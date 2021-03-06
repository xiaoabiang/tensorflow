# Description:
#   Contains ops for statistical distributions (with pdf, cdf, sample, etc...).
#   APIs here are meant to evolve over time.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//tensorflow:__subpackages__"])

load("//tensorflow:tensorflow.bzl", "cuda_py_test")

py_library(
    name = "distributions_py",
    srcs = ["__init__.py"] + glob(["python/ops/*.py"]),
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/contrib/framework:framework_py",
        "//tensorflow/contrib/linalg:linalg_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:check_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:control_flow_ops",
        "//tensorflow/python:data_flow_ops",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:linalg_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:random_ops",
        "//tensorflow/python:special_math_ops",
        "//third_party/py/numpy",
        "@six_archive//:six",
    ],
)

cuda_py_test(
    name = "distribution_test",
    size = "small",
    srcs = ["python/kernel_tests/distribution_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:random_ops",
    ],
)

cuda_py_test(
    name = "conditional_distribution_test",
    size = "small",
    srcs = [
        "python/kernel_tests/conditional_distribution_test.py",
        "python/kernel_tests/distribution_test.py",
    ],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:random_ops",
    ],
)

cuda_py_test(
    name = "operator_pd_test",
    size = "small",
    srcs = ["python/kernel_tests/operator_pd_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:linalg_ops",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "operator_pd_cholesky_test",
    size = "medium",
    srcs = ["python/kernel_tests/operator_pd_cholesky_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "operator_pd_diag_test",
    size = "medium",
    srcs = ["python/kernel_tests/operator_pd_diag_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "@six_archive//:six",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "operator_pd_full_test",
    size = "medium",
    srcs = ["python/kernel_tests/operator_pd_full_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "operator_pd_identity_test",
    size = "medium",
    srcs = ["python/kernel_tests/operator_pd_identity_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "operator_pd_vdvt_update_test",
    size = "large",
    srcs = ["python/kernel_tests/operator_pd_vdvt_update_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
    shard_count = 5,
    tags = ["notap"],  # http://b/30441813
)

cuda_py_test(
    name = "bernoulli_test",
    size = "small",
    srcs = ["python/kernel_tests/bernoulli_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "beta_test",
    size = "small",
    srcs = ["python/kernel_tests/beta_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "binomial_test",
    size = "small",
    srcs = ["python/kernel_tests/binomial_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "categorical_test",
    size = "small",
    srcs = ["python/kernel_tests/categorical_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:random_ops",
    ],
)

cuda_py_test(
    name = "chi2_test",
    srcs = ["python/kernel_tests/chi2_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "dirichlet_test",
    size = "small",
    srcs = ["python/kernel_tests/dirichlet_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "dirichlet_multinomial_test",
    size = "medium",
    srcs = ["python/kernel_tests/dirichlet_multinomial_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "exponential_test",
    srcs = ["python/kernel_tests/exponential_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "gamma_test",
    srcs = ["python/kernel_tests/gamma_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "inverse_gamma_test",
    srcs = ["python/kernel_tests/inverse_gamma_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "laplace_test",
    srcs = ["python/kernel_tests/laplace_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "multinomial_test",
    srcs = ["python/kernel_tests/multinomial_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "mvn_test",
    size = "small",
    srcs = ["python/kernel_tests/mvn_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "mixture_test",
    size = "medium",
    srcs = ["python/kernel_tests/mixture_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/core:protos_all_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:random_ops",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "normal_test",
    size = "medium",
    srcs = ["python/kernel_tests/normal_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:gradients",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "poisson_test",
    size = "small",
    srcs = ["python/kernel_tests/poisson_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "student_t_test",
    size = "small",
    srcs = ["python/kernel_tests/student_t_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:nn_ops",
        "//tensorflow/python:platform_test",
    ],
    tags = ["nomsan"],  # disable to avoid false positives from scipy.
)

cuda_py_test(
    name = "vector_student_t_test",
    size = "medium",
    srcs = ["python/kernel_tests/vector_student_t_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "uniform_test",
    size = "small",
    srcs = ["python/kernel_tests/uniform_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
    ],
)

cuda_py_test(
    name = "wishart_test",
    size = "small",
    srcs = ["python/kernel_tests/wishart_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:errors",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "kullback_leibler_test",
    size = "small",
    srcs = ["python/kernel_tests/kullback_leibler_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "normal_conjugate_posteriors_test",
    size = "small",
    srcs = ["python/kernel_tests/normal_conjugate_posteriors_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "quantized_distribution_test",
    size = "medium",
    srcs = ["python/kernel_tests/quantized_distribution_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:gradients",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "logistic_test",
    size = "small",
    srcs = ["python/kernel_tests/logistic_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "relaxed_bernoulli_test",
    size = "small",
    srcs = ["python/kernel_tests/relaxed_bernoulli_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "onehot_categorical_test",
    size = "small",
    srcs = ["python/kernel_tests/onehot_categorical_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "relaxed_onehot_categorical_test",
    size = "small",
    srcs = ["python/kernel_tests/relaxed_onehot_categorical_test.py"],
    additional_deps = [
        ":distributions_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "transformed_distribution_test",
    size = "medium",
    srcs = ["python/kernel_tests/transformed_distribution_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/linalg:linalg_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "conditional_transformed_distribution_test",
    size = "medium",
    srcs = [
        "python/kernel_tests/conditional_transformed_distribution_test.py",
        "python/kernel_tests/transformed_distribution_test.py",
    ],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/contrib/linalg:linalg_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "special_math_test",
    size = "medium",
    srcs = ["python/kernel_tests/special_math_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:gradients",
        "//tensorflow/python:platform_test",
        "//tensorflow/python:variables",
    ],
)

cuda_py_test(
    name = "distribution_util_test",
    size = "small",
    srcs = ["python/kernel_tests/distribution_util_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:gradients",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "shape_test",
    size = "small",
    srcs = ["python/kernel_tests/shape_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

cuda_py_test(
    name = "bijector_test",
    size = "medium",
    srcs = ["python/kernel_tests/bijector_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "@six_archive//:six",
        "//tensorflow/contrib/linalg:linalg_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
    shard_count = 5,
)

cuda_py_test(
    name = "conditional_bijector_test",
    size = "medium",
    srcs = ["python/kernel_tests/conditional_bijector_test.py"],
    additional_deps = [
        ":distributions_py",
        "//third_party/py/numpy",
        "@six_archive//:six",
        "//tensorflow/contrib/linalg:linalg_py",
        "//tensorflow/python:array_ops",
        "//tensorflow/python:client_testlib",
        "//tensorflow/python:framework_for_generated_wrappers",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:math_ops",
        "//tensorflow/python:platform_test",
    ],
    shard_count = 5,
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
