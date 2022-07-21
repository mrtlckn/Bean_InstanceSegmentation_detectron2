# Bean and Cucumber InstanceSegmentation

<aside>
📖 **Detectron2**, **LabelMe, GoogleColab**

Bu projede Instance Segmentation  ile 3 adet çalışma yapılmıştır.
1- Bean Instance Segmentation 
16 Adet resim üzerinden 48 adet etiketlenmiş bezelyeden oluşuyor.

2- Bean Instance Segmentation
1 Adet resim üzerinden 3 adet etkilenmiş bezelyeden oluşuyor.

3- Bezelye ve Salatalık Instance Segmentation (10.000 iteration)
48 Adet etiketlenmiş Bezelye ve +100 Adet etiketlenmiş Salatalık resminden oluşuyor

Projenin Amacı : Instance Segmentation ile tek sınıf ve 2 adet sınıf  için en uygun etiketlenmiş obje, resim ve iterasyon sayısının tespiti.

[GitHub - mrtlckn/Bean_InstanceSegmentation_detectron2](https://github.com/mrtlckn/Bean_InstanceSegmentation_detectron2)

</aside>

- 1- Bean Instance Segmentation
    
    [Bean_InstanceSegmentation_detectron2/Bean_InstanceSegmention.ipynb at main · mrtlckn/Bean_InstanceSegmentation_detectron2](https://github.com/mrtlckn/Bean_InstanceSegmentation_detectron2/blob/main/Bean_InstanceSegmention.ipynb)
    
    - Kod ve Sonuç
        
        Modelimizi 48 adet etiketlenmiş resim ile eğittik.
        
        ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled.png)
        
        Aşağıdaki bezelye görüntüsünün sonucu beklendiği gibi geldi.
        
        ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%201.png)
        
        ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%202.png)
        
- 2- Bean Instance Segmentation ( 3 etiket ile)
    
    [Bean_InstanceSegmentation_detectron2/Bean_training_with_just_one_image.ipynb at main · mrtlckn/Bean_InstanceSegmentation_detectron2](https://github.com/mrtlckn/Bean_InstanceSegmentation_detectron2/blob/main/Bean_training_with_just_one_image.ipynb)
    
    İlk projemizde etkili bir sonuca ulaştık, 3 etiketli resim ile modelimizi tekrar test ediyoruz.
    Model ve kodlarımız aynı.
    
    - Sonuç
    3 adet etiketlenmiş resim ile eğitilen modelimiz bize düşük oranda tahmin yapabiliyor ama tatmin edici değil.
        
        ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%203.png)
        
- 3-Bezelye ve Salatalık Instance Segmentation (10.000 iteration)
    
    [Bean_InstanceSegmentation_detectron2/Bean_Cucumber_it10000.ipynb at main · mrtlckn/Bean_InstanceSegmentation_detectron2](https://github.com/mrtlckn/Bean_InstanceSegmentation_detectron2/blob/main/Bean_Cucumber_it10000.ipynb)
    
    1. Daha önceki projelerimizde iterasyon sayımız 1.000 adetti, fakat 2 adet sınıf için doğruluk oranımız çok düşük geldi. Ben de iterasyon sayımızı 10 katına çıkarttım.
    2. 48 Adet etiketlenmiş Bezelye resmimiz ve +100 adet Salatalık resimimiz ile model eğitimi gerçekleşti.
    - Kod ve sonuç
        1. 10.000 iterasyon sonunda model eğitimimiz 75dakika sürdü.
        2. total_loss = 0.3277 oldu, iterasyon sayısını arttırarak veya etiketlenmiş resim sayımızda oynama yaparak lossumuzu düşürebiliriz.
        
        ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%204.png)
        
        - Diğer projelerimizde kullandığımız test resminin sonucu;
            
            ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%205.png)
            
            İlk projemiz gibi çok sayıda bezelye bulamadı fakat tespit edilenlerin doğruluk oranı yüksek.
            
        - Salatalık resminin sonucu
            
            Test sonucumuz başarısız oldu. 
            
            ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%206.png)
            
        - Salatalık resminin sonucu 2
            
            Bazı salatalıklar çok net olduğu halde başarısız oldu.
            
            ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%207.png)
            
        - Salatalık resminin sonucu 3
            
            Resimde bir insan salatalık tutuyor, tahminimiz çok karışmış halde
            
            ![Untitled](Bean%20and%20Cucumber%20InstanceSegmentation%20726c6319f3bb4154be067c51b6b87459/Untitled%208.png)
            
        - Sonuç
            
            Modelimiz etkili çalışmıyor. İlk projemizde 48 adet etiketlenmiş resim ile bezelye tespitimiz yüksek doğruluk oranında çalışıyordu fakat modeli bezelye+salatalık olarak eğitince düşük doğruluk oranında çalışıyor ve daha önce yaptığı doğru tahminleri yapamıyor.
            
            Bu sorunu aşmak için yapılabilecek olan maddeler;
            
            1. Sınıfımızdaki etiketlenmiş resimlerimiz aynı oranda değildi (48 adet ve+100 adet)
            2. Etiketlenmiş resimlerimizin sayısını arttırmamız lazım.
            3.  İterasyon sayısında artışa gidilebilir fakat model eğitim süreside artıyor.
        

-
