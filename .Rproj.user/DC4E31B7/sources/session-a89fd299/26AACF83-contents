dsvmf <- function(y, mu, a, kappa, Gamma = NULL, log = FALSE) {
  y <- if ( is.matrix(y) ) y else matrix(y, nrow = 1)
  p <- ncol(y)  ;  q <- p - 1
  a1 <- a[1]
  a <- c(a1, a[-1] / prod(a[-1])^(1/q))
  mu <- mu / sqrt(sum(mu^2))

  if ( is.null(Gamma) ) {
    e1 <- c(1, numeric(q))
    if ( max(abs(mu - e1)) < 1e-12 ) {
      Gamma <- diag(p)
    } else {
      u <- (e1 - mu) / sqrt(sum((e1 - mu)^2))
      Gamma <- diag(p) - 2 * tcrossprod(u)
    }
  }

  z  <- y %*% Gamma
  s2 <- rowSums( sweep(z, 2, a, "/")^2 )

  nu <- p / 2 - 1
  log_c <- nu * log(kappa) - (p / 2) * log(2 * pi) -
    ( log( besselI(kappa, nu, expon.scaled = TRUE) ) + kappa )

  ld <- log_c - sum(log(a)) - (p / 2) * log(s2) + kappa / a1 * z[, 1] / sqrt(s2)
  if ( log ) ld else exp(ld)
}
