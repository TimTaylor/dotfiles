invisible(local(
    {
        # use Rstudio cran repos
        r <- getOption("repos")
        r["CRAN"] <- "https://cran.rstudio.com/"
        options(repos = r)

        if (interactive()) {

            # CRAN package statuses
            if (stats::runif(1)<0.2 && requireNamespace("dang", quietly=TRUE)) {
                EMAIL <- intToUtf8(
                    c(116L, 105L, 109L, 46L, 116L, 97L, 121L, 108L, 111L, 114L,
                      64, 104L, 105L, 100L, 100L, 101L, 110L, 101L, 108L, 101L,
                      112L, 104L, 97L, 110L, 116L, 115L, 46L, 99L, 111L, 46L,
                      117L, 107L)
                )
                dang::checkCRANStatus(EMAIL)
            }

            # Enables backtraces for all errors!
            if (requireNamespace("rlang", quietly = TRUE)) {
                options(error = rlang::entrace)
            }

            # enable autocompletions for package names in `require()`, `library()`
            utils::rc.settings(ipck = TRUE)

            options(
                Ncpus = 4,
                prompt = "R> ",
                editor = "nano",
                useFancyQuotes = FALSE,
                datatable.print.nrows = 10,
                warnPartialMatchAttr = TRUE,
                warnPartialMatchDollar = TRUE,
                warnPartialMatchArgs = TRUE
            )
        }
    }
))
