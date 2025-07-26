# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.from pypokerengine.api.game import setup_game, start_poker
from pypokerengine.players import BasePokerPlayer, RandomPlayer, FishPlayer

class MyAI(BasePokerPlayer):
    def declare_action(self, valid_actions, hole_card, round_state):
        return 'CALL', 0
    def receive_round_result_message(self, winners, hand_info, round_state):
        pass

game_config = setup_game(
    max_round=500,
    initial_stack=1000,
    small_blind_amount=10,
    players=[
        {"name": "AI‑1", "algo": MyAI()},
        {"name": "Random1", "algo": RandomPlayer()},
        {"name": "Random2", "algo": RandomPlayer()},
        {"name": "Fish1", "algo": FishPlayer()},
        {"name": "Fish2", "algo": FishPlayer()},
    ]
)

result = start_poker(game_config)
print(result)

