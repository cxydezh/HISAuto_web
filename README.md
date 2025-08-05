# HISAuto_web
用于deepseek的AI模型调用
# HISAuto_web
用于deepseek的AI模型调用
请帮我设计一款前段应用，要求如下：
*1.命名：HISAuto_web。标题：住院部HIS Agent应用。
*2.采用B/S架构，后台数据库拟采用Sqlite，但是目前先不要用。请先试用硬代码编写示例数据，所有的实例数据放在一个单独文件中（data_display)。
*3.数据传输采用：TCP传输，暂时先不设计。
*4.程序入口：登录界面，设置的实例账号：admin，密码：admin。登录界面设计要按照实际应用场景设计。
*5.登录成功后，进入主要工作界面。
*6.工作界面分为2大部分，分别对应2个Tab页，横向布局，分别为：工作台、设置。
*7.工作台Tab：界面采用grid模式，主要分左右两部分，左侧的宽度为右侧宽度的三分之一，命名为：left_panel，右侧命名为：right_panel。
*8.Left_panel:呈上下结构布局，第一行是一个按钮，标题为：更新Excel文件。第二行为一个combo控件，其中默认的内容有：个人、肾病科、呼吸内科、心血管内科。第3行为一个List控件（名称为：patient_list)，列表中显示4列数据：ID、姓名、入院日期。当第二行选择不同的科室时，第三行数据会随之更新。程序中嵌入不同科室的示例数据，至少5条。
*9.right_panel:改区域包含3个标签（横向布局），名称分别为：info_tab、AI_function_tab、AI_result_tab。标题分别为：基本信息、AI功能区、AI结果区。当选择patient_list控件中的患者信息时，患者的基本信息就会在info_fo中显示。AI功能区的可以加载预先设计好的AI功能模块。AI结果区显示AI功能区运行后的结果。
*10.info_tab中显示的信息包括：患者姓名、年龄、性别、入院科室、入院时间、入院天数、主管医生、住院医生、主治医生、备注信息。
*11.AI_function_tab中主要分左右2部分——AI_left_section、AI_right_section。AI_left_section宽度是AI_right_section的三分之一。AI_left_section中控件呈上下分布。第一行为一个combo控件，命名为：AI_selection，标题为：AI功能选择。下方为一个树形控件，显示内容根据AI_selection内容的选择而更新。AI_right_section呈上下布局，第一行显示1个横向布局的单选控件（包含两个选项——单项、组群）和一个按钮，标题为运行，点击运行后，会在AI_result_tab中显示程序的运行结果。第二行为一个富文本控件，当选择树形控件中的条目时，右侧AI_right_section中的富文本控件会显示该条目的备注信息。
*12.AI_result_Tab显示AI_function_tab中AI项目运行过程及结果，布局为左右2部分——result_left、result_right。其中result_left宽度为result_right的三分之一。result_left为一个列表控件，显示内容为2列，第一列内容为AI_function_tab中树形控件的中选择项目的名称，第二列为该项目的运行时间。result_right为上下布局，主要分2部分——AI_progress、AI_result。AI_progress主要显示AI_function_tab中树形结构中的项目运行时的过程监控信息。AI_result为富文本控件，显示运行后的结果。
*13.设置Tab主要显示修改密码相关的内容。
*14.当点击左侧患者列表信息后，右侧的基本信息和AI_result均会发生更新。
*15.AI_function_tab中树形控件显示的内容为一个由列表型的数据（func_list)组成的字典型据(func_group)。树形控件显示的内容为key的内容。func_list数据，是一个工作流格式的数据，是一个有顺序的数据结构组成的列表，其中包含的数据是字典格式的数据，该字典包含3个key：AI运行过程名、AI运行过程备注、AI运行的模拟延迟时间。当在AI_function_tab中点击运行按钮后，在AI_function_tab中的AI_progress中可以看到选中的func_list数据运行工作流的动画。
*16.AI_function_tab中的AI_selection控件显示的列表是data_display.py中的一个元祖数据（suit_type,即套餐类型)，该元祖数据包含3个字符串分别为“个人”、“科室"、”全局"。下方树形控件显示的内容为一个由列表型的数据（func_list)组成的字典型据(func_group)。树形控件显示的内容为key的内容。key_value是由三个字典类型的数据组成的集合数据（func_set)。第一个字典数据的key为：fun_list_name，其key_value为func_list数据；第二个字典数据的key为：func_list_type，其key_value为标记该func_list的内容属于哪个套餐类型的字符串类型数据。第三个字典数据的key为：AI_prompt，其内容为字符串类型的数据，用来存储一段AI大模型提示词。当AI_selection中的内容更新时，下方的树形控件内容也会随之更新。当选中树形控件中的内容后，AI_right_section中第二行的富文本控件显示选中的func_set中的第三个字典数据的内容，即AI_prompt对应的内容。func_set中的func_list数据，是一个有工作流功能的数据，是一个有数据结构有顺序的列表数据，其中包含的数据是字典格式的数据，该字典包含3个key：AI运行过程名、AI运行过程备注、AI运行的模拟延迟时间。当选中树形控件的item时，在AI_function_tab中点击运行按钮后，在AI_function_tab中的AI_progress中就可以看到选中的func_list数据运行工作流的模拟动画。
17.要求设计的界面具有现代性，动画显示美观、大气。
