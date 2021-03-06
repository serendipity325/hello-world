# Kneser-Ney trigram model


<main functions>

get_words(x) is a function to manipulate train and test files.<br />
get_ngrams(words) generates unigram, bigram, trigram, N1+(Wi-1, *), N1+(*, Wi), N1+(Wi-2, Wi-1, *),
N1+(*, Wi-1, Wi), and N1+(*, Wi-1, *).<br />

Kneser_Ney1 is the function for computing original version of trigram Kneser-Ney smoother.<br /> 
Kneser_Ney2 is the function for computing revised version of trigram Kneser-Ney smoother.<br />

get_KN1 is the function for computing probability and perplexcity of original version of trigram Kneser-Ney smoother,
and generating list of trigram Kneser-Ney smoothers.<br />

get_KN2 is the function for computing probability and perplexcity of revised version of trigram Kneser-Ney smoother,
and generating list of trigram Kneser-Ney smoothers.<br />


************ Output ************

original version of trigram Kneser-Ney Smoothing is

max[C(Wi-2, Wi-1, Wi) - d, 0] / C(Wi-2, Wi-1) + (d * N1+(Wi-2, Wi-1, .) / C(Wi-2, Wi-1)) * K,
where K = max[C(Wi-1, Wi) -d, 0] / C(Wi-1) + (d * N1+(Wi-1, .) * N1+(., Wi)/ C(Wi-1) / N1+(., .))

revised version is

max[C(Wi-2, Wi-1, Wi) - d, 0] / C(Wi-2, Wi-1) + (d * N1+(Wi-2, Wi-1, .) / C(Wi-2, Wi-1)) * K,
where K = max[N1+(., Wi-1, Wi) -d, 0] / N1+(., Wi-1, .) + (d * N1+(Wi-1, Wi) * N1+(., Wi)/ N1+(., Wi-1, .) / N1+(., .))

Below is each result with d = 0.5.

Result with original version of probability of bigram Kneser-Ney Smoothing: P_2(Wi|Wi-1)

total log(p_kn) = -304802.752703<br />
Perplexity      = 245.170541263<br />


Result with revised version of probability of bigram Kneser-Ney Smoothing: P_2(Wi|Wi-1)

total log(p_kn) = -315568.855508<br />
Perplexity      = 297.761118337<br />

-----------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------


The next result is with d = 0.9 for original and d = 07 for revision.

Result with original version of probability of bigram Kneser-Ney Smoothing: P_2(Wi|Wi-1)

total log(p_kn) = -301348.39976<br />
Perplexity      = 230.35002236<br />


Result with revised version of probability of bigram Kneser-Ney Smoothing: P_2(Wi|Wi-1)

total log(p_kn) = -315003.886508<br />
Perplexity      = 294.73992822<br />

