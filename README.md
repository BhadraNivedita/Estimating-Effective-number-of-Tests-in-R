# Estimating-Effective-number-of-Tests-in-R

The function estimates the effective number of tests based on one of four different methods. All methods work by extracting the eigenvalues from the $\(R\)$ matrix supplied via the $R$ argument (or from the eigenvalues directly passed via the eigen argument). Letting $\(\lambda_i\)$ denote the \(i\)th eigenvalue of this matrix (with \(i = 1, \ldots, k\)) in decreasing order, the effective number of tests $(\(m\))$ is estimated as follows.


### Method by Nyholt (2004)

$\[m = 1 + (k - 1) \left(1 - \frac{\mbox{Var}(\lambda)}{k}\right)\]$
where $\(\mbox{Var}(\lambda)\)$ is the observed sample variance of the \(k\) eigenvalues.

### Method by Li & Ji (2005)

$\[m = \sum_{i = 1}^k f(|\lambda_i|)\]$
where $\(f(x) = I(x \ge 1) + (x - \lfloor x \rfloor)\) $ and $\(\lfloor \cdot \rfloor\)$ is the floor function.

### Method by Gao et al. (2008)

$\[m = \min(x) \; \mbox{such that} \; \frac{\sum_{i = 1}^x \lambda_{i}}{\sum_{i = 1}^k \lambda_{i}} > C\]$
where $\(C\)$ is a pre-defined parameter which is set to $0.995$ by default.

### Method by Galwey (2009)

$\[m = \frac{\left(\sum_{i = 1}^k \sqrt{\lambda_i'}\right)^2}{\sum_{i = 1}^k \lambda_i'}\]$
where $\(\lambda_i' = \max[0, \lambda_i]\)$.
 
 ## What is the R matrix?
 
 Specifying the R Matrix

The $\(R\)$ matrix should reflect the dependence structure among the tests. There is no general solution on how such a matrix should be constructed, as this depends on the type of test and the sidedness of these tests. For example, we can use the correlations among related but changing elements across the analyses/tests, or a function thereof, as a proxy for the dependence structure. For example, when conducting \(k\) analyses with the same dependent variable and $\(k\)$ different independent variables, the correlations among the independent variables could serve as such a proxy. Analogously, if analyses are conducted for $\(k\)$ dependent variables with the same set of independent variables, the correlations among the dependent variables could be used instead.

If the tests of interest have test statistics that can be assumed to follow a multivariate normal distribution and a matrix is available that reflects the correlations among the test statistics (which might be approximated by the correlations among the interchanging independent or dependent variables), then the mvnconv function can be used to convert this correlation matrix into the correlations among the (one- or two-sided) \(p\)-values, which in turn can then be passed to the R argument. See ‘Examples’.
