<?php
/*
	 * 按周次分配该年月的日期
	 * $param = date('Y-m-d');
	 * return array()
	 */
	public static function getDaysByWeekOfMonth($dateParam='2019-05-24'){
		
		$monthWeekArr = array();
		//这个月1号是星期几
		$weekDayOf1st = date('w',strtotime(date('Y-m-1',strtotime($dateParam))));
		//本月
		$month = date('Y-m',strtotime(date('Y-m-1',strtotime($dateParam))));

        //如果这个月1号是星期日，设为7
		if(!$weekDayOf1st) $weekDayOf1st=7;
		$firstWeekDays = $weekDayOf1st==7 ? 1 : 8-$weekDayOf1st; #本月第一周有几天，如果$weekDayOf1st=7，就是星期日，只有1天。
		//这个月有几天
		$daysOfMonth = date('t',strtotime($dateParam));
		$w =  1;
		$n = 0;
		for($i=1; $i<=$daysOfMonth; $i++){
			$d = $i<10 ? '-0'.$i : '-'.$i;
			$monthWeekArr[$w][] = $month.$d;
			if($w==1 && $firstWeekDays==$i){
				$w++;
				continue;
			}
			if($w>1){
			    $n++;
                if($n%7==0){
                    $w++;
                }
            }
		}
		return $monthWeekArr;
	}
?>
