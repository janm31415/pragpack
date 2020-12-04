# PrAGPack: Pragmatic Algebra Gems Package

Note: pragpack is deprecated. 
It has been replaced by the header-only file [mat.h in jtk](https://github.com/janm31415/jtk/blob/master/jtk/mat.h).


Single header file matrix library using expression templates.

The basic matrix type is
```
  template <class T, class Container>
  class matrix;
```
Here parameter `T` should be a numeric type such as `float` or `double`.
Container should be `std::vector<T>` for dynamic allocation or `std::array<T, size>`
for small sized matrices.

The most common usages are typedef-ed:
```
  typedef matrix<double> mat;
  typedef matrix<float> matf;
  
  typedef matrix<double, std::array<double, 1>> mat1;
  typedef matrix<double, std::array<double, 2>> mat2;
  typedef matrix<double, std::array<double, 3>> mat3;
  ...
  typedef matrix<float, std::array<float, 1>> matf1;
  typedef matrix<float, std::array<float, 2>> matf2;
  typedef matrix<float, std::array<float, 3>> matf3;
  ...
```

Vectors are not a separate class, but are matrices with 1 row or 1 column.

Many common matrix algorithms are available:
- matrix and vector arithmetic
- matrix transpose
- svd (singular value decomposition)
- pseudo inverse
- lsd (solves overdetermined systems in a least squares sense using svd)
- lu decomposition
- solve a system using lu decomposition
- invert a matrix using lu decomposition
- cholesky factorization
- solve a system using cholesky factorization
- qr decomposition
- solve a system using qr decomposition
- frobenius norm
- compute a jacobian matrix using forward differences
- levenberg-marquardt optimization
- eigenvalue computation of square matrices
