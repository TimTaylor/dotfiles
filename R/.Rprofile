invisible(local({

    # use Rstudio cran repos
    r <- getOption("repos")
    r["CRAN"] <- "https://cran.rstudio.com/"
    options(repos = r)

    if (interactive()) {

        loadhistory(file = "~/.Rhistory")

        suppressMessages(require(devtools))
        suppressMessages(require(coffee))
        firstname <- intToUtf8(c(84L, 105L, 109L))
        surname   <- intToUtf8(c(84L, 97L, 121L, 108L, 111L, 114L))
        name      <- paste(firstname, surname)
        email     <- intToUtf8(c(116L, 105L, 109L, 46L, 116L, 97L, 121L, 108L,
                                 111L, 114L, 64L,  104L, 105L, 100L, 100L, 101L,
                                 110L, 101L, 108L, 101L, 112L, 104L, 97L, 110L,
                                 116L, 115L, 46L, 99L, 111L, 46L, 117L, 107L))


        # CRAN package statuses
        if (stats::runif(1) < 0.2 && requireNamespace("dang", quietly = TRUE))
            dang::checkCRANStatus(email)

        # Enables backtraces for all errors!
        if (requireNamespace("rlang", quietly = TRUE))
            options(error = rlang::entrace)

        options(Ncpus = 4,
                prompt = "R> ",
                editor = "nano",
                useFancyQuotes = FALSE,
                warnPartialMatchAttr = TRUE,
                warnPartialMatchDollar = TRUE,
                warnPartialMatchArgs = TRUE,
                coffee.firstname = firstname,
                coffee.surname = surname,
                coffee.name = name,
                coffee.email = email,
                usethis.protocol = "ssh")

        # enable autocompletions for package names in `require()`, `library()`
        utils::rc.settings(ipck = TRUE)

    }

}))

.Last <- function() {
    if (interactive()) try(savehistory("~/.Rhistory"))
}
