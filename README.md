# Strategy7_Bull-Bear-Spread-with-adjusments
Semi-Directional,Momentum

Instrument:NIFTYBANK
Heikin Ashi
Timeframe:5m
Capital required:300k inr
Segment:Options
Expiry: Weekly

Logic:
Works as a bear/bull spread but with adjustments.

Set1
Conditions:
1.Time>=926
2.Close of previous candle > Supertrend of previous candle (defined parameters above)

Position:
Leg1 = Buy,NIFTYBANK,75rs,10lot,PE
Leg2 = Buy,NIFTYBANK,75rs,5lot,CE
Leg3 = Sell,NIFTYBANK,150rs,10lot,PE
Leg4 = Sell,NIFTYBANK,150rs,5lot,CE

Note: 1.Make sure the buying position are executed first, so less margin is consumed.
      2.Here, "75rs,150rs" means option strike worth 75,150rs.
      
Repair 1: When leg 3 gains 30% of the premium, exit leg 3 and take the same position again.
Repair 2: When leg 4 gains 30% of the premium, exit leg 4 and take the same position again.
Repair 3: When Repair 1 position has gained 30% of premium, exit the repair 1 leg and take the same position again.
Repair 4: When Repair 2 position has gained 30% of premium, exit the repair 2 leg and take the same position again.
Repair 5: When Repair 3 position has gained 30% of premium, exit the repair 3 leg and take the same position again.

Note: 1.Make the same set for oppsite side(CE)
      2.Each set has individual sl of 3k inr.
      3.Once one set sl is hit, the strategy will take the new position according to the chart. Do note the strategy will only run twice.
      
Universal exit:
PNL<= -6000
Time>=1515
  


Disclaimer :  I am not a SEBI registered investment or financial advisor. Don't deploy our strategies purely based on past performance only. We are not responsible for your profit or loss. Although this strategy is fully automated, you are advised to keep a track on your account to monitor any deviations or errors. As option selling involves market risks, Please consult your financial advisor before investing.


Disclaimer: This is a algorithmic strategy which is also my personal project which is coded on tradetron, for codes ping me up.
