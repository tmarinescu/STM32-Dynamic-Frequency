# STM32 Dynamic Frequency

Just a quick concept test for myself to see if deploying such a system in SDOS is viable. All it does is cycle between different clock speeds while doing something (delaying and toggling LED).


It takes 15ms on average to switch clock (using PLL). Interesting part is that it takes 1ms to switch the PLL off and go back directly to the HSI.

It uses ST's HAL API which makes me suspicious of the actual time due to overhead and how badly written the API is in general. According to the API you
cannot mess with the PLL once it's in use and this requires further investigation because I don't believe it for one second. The next step is a low-level implementation and 
some manual reading.

In conclusion, it's viable.
