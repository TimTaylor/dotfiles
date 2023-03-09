invisible(local({

    # use Rstudio cran repos
    r <- getOption("repos")
    r["CRAN"] <- "https://cran.rstudio.com/"
    options(repos = r)

    if (interactive()) {

        # always useful
        suppressMessages(require(devtools, quietly = TRUE))

        # exclude assertions which shouldn't really be in ympes
        without <- c(
            "assert_bool", "assert_boolean",
            "assert_character", "assert_chr",
            "assert_data_frame",
            "assert_dbl", "assert_double",
            "assert_int", "assert_integer",
            "assert_lgl", "assert_logical",
            "assert_list",
            "assert_num", "assert_numeric",
            "assert_scalar_character", "assert_scalar_chr", "assert_string",
            "assert_scalar_dbl", "assert_scalar_double",
            "assert_scalar_int", "assert_scalar_integer",
            "assert_scalar_lgl", "assert_scalar_logical",
            "assert_scalar_num", "assert_scalar_numeric",

            "imp_assert_bool", "imp_assert_boolean",
            "imp_assert_character", "imp_assert_chr",
            "imp_assert_data_frame",
            "imp_assert_dbl", "imp_assert_double",
            "imp_assert_int", "imp_assert_integer",
            "imp_assert_lgl", "imp_assert_logical",
            "imp_assert_list",
            "imp_assert_num", "imp_assert_numeric",
            "imp_assert_scalar_character", "imp_assert_scalar_chr",
            "imp_assert_string",
            "imp_assert_scalar_dbl", "imp_assert_scalar_double",
            "imp_assert_scalar_int", "imp_assert_scalar_integer",
            "imp_assert_scalar_lgl", "imp_assert_scalar_logical",
            "imp_assert_scalar_num", "imp_assert_scalar_numeric"
        )
        suppressMessages(require(ympes, quietly = TRUE, exclude = without))
        firstname <- intToUtf8(c(84L, 105L, 109L))
        surname <- intToUtf8(c(84L, 97L, 121L, 108L, 111L, 114L))
        email <- intToUtf8(c(
            116L, 105L, 109L, 46L, 116L, 97L, 121L, 108L, 111L, 114L, 64L,
            104L, 105L, 100L, 100L, 101L, 110L, 101L, 108L, 101L, 112L, 104L,
            97L, 110L, 116L, 115L, 46L, 99L, 111L, 46L, 117L, 107L
        ))
        orcid <- "0000-0002-8587-7113"

        # CRAN package statuses
        if (stats::runif(1) < 0.2 && requireNamespace("dang", quietly = TRUE))
            dang::checkCRANStatus(email)

        # Enables backtraces for all errors!
        if (requireNamespace("rlang", quietly = TRUE))
            options(error = rlang::entrace)

        options(
            ympes.firstname = firstname,
            ympes.surname = surname,
            ympes.email = email,
            ympes.orcid = orcid,
            Ncpus = 4,
            prompt = "R> ",
            editor = "nano",
            useFancyQuotes = FALSE,
            warnPartialMatchAttr = TRUE,
            warnPartialMatchDollar = TRUE,
            warnPartialMatchArgs = TRUE,
            usethis.protocol = "ssh",
            usethis.full_name = paste(firstname, surname),
            imp.clipboard = TRUE
        )

        # enable autocompletions for package names in `require()`, `library()`
        utils::rc.settings(ipck = TRUE)

    }

}))
