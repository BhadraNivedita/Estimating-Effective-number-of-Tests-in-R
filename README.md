# Estimating-Effective-number-of-Tests-in-R




Method by Nyholt (2004)

$\[m = 1 + (k - 1) \left(1 - \frac{\mbox{Var}(\lambda)}{k}\right)\]$
where $\(\mbox{Var}(\lambda)\)$ is the observed sample variance of the \(k\) eigenvalues.

Method by Li & Ji (2005)

$\[m = \sum_{i = 1}^k f(|\lambda_i|)\]$
where $\(f(x) = I(x \ge 1) + (x - \lfloor x \rfloor)\) $ and $\(\lfloor \cdot \rfloor\)$ is the floor function.

Method by Gao et al. (2008)

$\[m = \min(x) \; \mbox{such that} \; \frac{\sum_{i = 1}^x \lambda_{i}}{\sum_{i = 1}^k \lambda_{i}} > C\]$
where $\(C\)$ is a pre-defined parameter which is set to $0.995$ by default.

Method by Galwey (2009)

$\[m = \frac{\left(\sum_{i = 1}^k \sqrt{\lambda_i'}\right)^2}{\sum_{i = 1}^k \lambda_i'}\]$
where $\(\lambda_i' = \max[0, \lambda_i]\)$.
