# NCU GS4519 Introduction to machine learning: final project

# 組員

陳佑宏, 嚴毅澤, 黃昱東, 林昱辰

# 小組目標

辨識食物熱量

# 本程式目標

以inception_v3做transfer learning，辨識101種食物，資料集共101000張圖片  
每種食物有1000張圖片，其中800張作為training資料、100張做為validation資料、100張作為testing資料

# 成果

1. 只跑了2個epoch，validation loss還在下降、validation accuracy還有上升趨勢，但由於時間有限，沒有繼續跑更多epoch、甚至fine tuning  
2. 最後成果是56% accuracy (有101種類別，隨便猜的話accuracy是1%)
3. 歡迎參考 prediction_demo_apple_pie_only.ipynb ，裡面的圖片的正確標籤都是蘋果派，看看它預測成什麼食物  
(如果跑出"Sorry, something went wrong. Reload?"，請按Reload幾次，可能跟裡面有100張蘋果派的圖有關)

# 準備方式

1. 使用inception_v3做transfer learning  
2. 資料集來源：https://www.kaggle.com/kmader/food41  
(這裡有其他人針對這筆資料的處裡，有興趣可以參考：https://www.kaggle.com/kmader/food41/notebooks)

main.ipynb參考：
1. https://www.itread01.com/content/1549244008.html
2. https://keras.io/api/applications/
3. 其他註解在main.ipynb中

其他程式參考：  
keras、tensorflow官方文件、stackoverflow問答

# 說明

1. main.ipynb： training，輸出model.h5(包括整個模型和其訓練完的權重)
2. inception layers.txt： 解凍inception_v3時查看層數
3. Moving_img_to_train_test_val.ipynb： Split all images into train(80%), validation(10%), test(10%) folders.
4. make_prediction.ipynb： 對test dataset做預測，讀取model.h5、輸出預測結果、輸出confusion matrix圖、輸出accuracy
5. prediction_demo_apple_pie_only.ipynb： 看看這些"蘋果派"
