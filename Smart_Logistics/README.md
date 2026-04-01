# dacon

🤖 Robot 상태 (핵심 그룹)
   robot_active, robot_idle, robot_charging, robot_utilization
   battery_mean, battery_std, low_battery_ratio
   charge_queue_length, avg_charge_wait
   avg_trip_distance, task_reassign_15m

📦 주문/물류
   order_inflow_15m, unique_sku_15m, avg_items_per_order
   urgent_order_ratio, heavy_item_ratio, cold_chain_ratio
   order_wave_count, pick_list_length_avg, bulk_order_ratio

🚧 혼잡/경로
   congestion_score, max_zone_density, blocked_path_15m
   near_collision_15m, path_optimization_score
   intersection_wait_time_avg, aisle_traffic_score

🏭 설비/환경
   warehouse_temp_avg, humidity_pct, lighting_level_lux
   hvac_power_kw, floor_vibration_idx, co2_level_ppm

⏱️ 시간 관련  ← 중요!
   shift_hour, day_of_week, prev_shift_volume




   [공통 선행 - 매번 동일]
0. 라이브러리 & 데이터 로드
1. Scenario-level Aggregation
2. 결측치 처리
3. Feature Engineering
4. 인코딩 & 불필요 컬럼 제거
        ↓
[실험 분기 - 여기서부터 다양하게]
5-A. model5 (현재 baseline)
5-B. sc_delay_mean_loo 추가 후 재학습
5-C. Optuna 튜닝
5-D. XGBoost/CatBoost 앙상블
...