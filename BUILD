load("@aspect_rules_py//py:defs.bzl", "py_pytest_main", "py_test")

py_pytest_main(
    name = "__test__",
    deps = ["@pypi//pytest:pkg"],
)

py_test(
    name = "pytest_test",
    srcs = [
        "foo_test.py",
        ":__test__",
    ],
    imports = [","],
    main = ":__test__.py",
    deps = [
        ":__test__",
        "@@pypi//nvfuser_cu121_torch21:pkg",
        "@pypi//torch:pkg",
    ],
)