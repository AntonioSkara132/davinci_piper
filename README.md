# davinci_piper
Model ruke AgileX Piper s adapterom za instrument da Vinci Si i ROS 2 datoteke koje ga povezuju sa SOFA simulacijom. Koristi se u Docker slici iz repozitorija [piper_davinci_simulation](https://github.com/AntonioSkara132/piper_davinci_simulation), gdje je kloniran u `/root/davinci_piper`; upute za pokretanje su ondje.

Nova verzija se u kontejneru dobiva bez ponovne izgradnje slike:
```bash
cd /root/davinci_piper && git pull
```

| Datoteka | Što je |
|---|---|
| `piper_davinci.urdf.xacro` | model: Piper + adapter |
| `davinci_adapter.urdf.xacro` | adapter i instrument s pomičnim zglobovima `instrument_roll`, `instrument_pitch`, `instrument_jaw_1`, `instrument_jaw_2` |
| `meshes/` | ovdje stavljate STL svog adaptera |
| `davinci_piper.launch.py` | robot_state_publisher, joint_state_merger, slideri, RViz |
| `davinci_piper.rviz` | postavke RViz-a |
| `joint_state_merger.py` | spaja zglobove ruke i adaptera u `/joint_states` |
| `piper_tool_bridge.py` | okviri instrumenta iz TF-a → UDP prema SOFA-i |
| `run_davinci_piper.sh` | naredba `run_davinci_piper`: ruka, most i SOFA scena |
| `tile_windows.sh` | slaže prozore |

## Licenca
[MIT](LICENSE)
