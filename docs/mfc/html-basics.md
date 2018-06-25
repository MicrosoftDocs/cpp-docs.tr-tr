---
title: HTML temelleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c4ebbc8e792e36461f7c52c17fa23815239e323
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929096"
---
# <a name="html-basics"></a>HTML Temelleri
Çoğu tarayıcı göz sayfaların HTML kaynağını inceleniyor özelliği var. HTML (Köprü Metni Biçimlendirme Dili) etiket sayısı görürsünüz kaynak görüntülediğinizde metinle interspersed açılı ayraçları (<>) tarafından çevrelenen.  
  
 Aşağıdaki adımlar, basit bir Web sayfası oluşturmak için HTML etiketlerini kullanın. Bu adımlarda, Not Defteri'nde dosyasına düz metin yazın, birkaç değişiklik, dosyayı kaydedin ve yaptığınız değişiklikleri görmek için tarayıcıda, sayfayı yeniden yükleyin.  
  
#### <a name="to-create-an-html-file"></a>Bir HTML dosyası oluşturmak için  
  
1.  Not Defteri'nde veya herhangi bir düz metin düzenleyicisini açın.  
  
2.  Gelen **dosya** menüsünde seçin **yeni**.  
  
3.  Aşağıdaki satırları yazın:  
  
 ```  
 <HTML>  
 <HEAD>  
 <TITLE>Top HTML Tags</TITLE>  
 </HEAD>  
 </HTML>  
 ```  
  
4.  Gelen **dosya** menüsünde seçin **kaydetmek**ve dosyayı c:\webpages\First.htm kaydedin. Dosyayı düzenleyicide açık bırakın.  
  
5.  Gelen ve tarayıcınız, anahtar **dosya** menüsünde seçin **açık**, veya türü *file://C:/webpages/first.htm* tarayıcının URL düzenleme kutusuna. Pencere resim yazısı "Üst HTML etiketleri." içeren boş bir sayfa görmeniz gerekir  
  
     Etiketler eşleştirilmelidir ve açılı ayraç içerdiği dikkat edin. Etiketler büyük küçük harfe duyarlı değildir, ancak büyük/küçük harf genellikle göze etiketleri yapmak için kullanılır.  
  
     Etiket \<HTML > belge ve etiket başlatır \</HTML > bunu sona erer. Bitiş etiketleri (her zaman gereklidir) başlangıç etiketi ile aynıdır, ancak bir eğik çizgi (/) etiketinin önünde sahip. Açılı ayraç (<), etiket başlangıcı arasındaki boşluk olmamalıdır.  
  
6.  Anahtarı not defteri dönün ve sonra  \< /HEAD > Satır, yazın:  
  
 ```  
 <BODY>  
    HTML is swell.  
    Life is good.  
 </BODY>  
 ```  
  
7.  Gelen **dosya** menüsünde seçin **kaydetmek**.  
  
8.  Tarayıcınızın geri geçin ve sayfayı yenileyin.  
  
     Sözcükler, tarayıcınızın pencere istemci alanında görüntülenir. Satır başı yoksayılır dikkat edin. Satır sonu sahip olmak istiyorsanız içermelidir bir `<BR>` ilk satırdan etiketi.  
  
     İzleyin, herhangi bir yere arasındaki metni Ekle tüm adımlar için \<gövde > ve  \< /BODY > belgenizi gövdesi eklenecek.  
  
9. Üstbilgi ekleyin:  
  
 ```  
 <H3>Here's the big picture</H3>  
 ```  
  
10. Sayfanız ile aynı dizinde kaydedilen .gif dosya kullanarak bir görüntü ekleyin:  
  
 ```  
 <IMG src="yourfile.gif">  
 ```  
  
11. Bir liste ekleyin:  
  
 ```  
 <UL>Make me an unordered list.  
 <LI>One programmer</LI>  
 <LI>Ten SDKs</LI>  
 <LI>Great Internet Apps</LI>  
 </UL>  
 ```  
  
12. Listenin yerine numara, kullanmak için eşleştirilmiş \<OL > ve \</OL > yerine etiketler \<UL > ve \</UL > etiketler.  
  
 Başlamanıza yardımcı. Bir Web sayfasında harika bir özellik görürseniz, HTML kaynağını inceleyerek oluşturulma çıkışı bulabilirsiniz. HTML düzenleyiciler Microsoft ön sayfa gibi basit ve Gelişmiş sayfaları oluşturmak için kullanılabilir.  
  
 Oluşturmakta dosya tüm HTML kaynağını şöyledir:  
  
```  
<HTML>  
<HEAD>  
<TITLE>Top HTML Tags</TITLE>  
</HEAD>  
<BODY>  
HTML is swell.<BR>  
Life is good.  
<H3>Here's the big picture</H3>  
<IMG src="yourfile.gif">  
<UL>Make me an unordered list.  
<LI>One programmer</LI>  
<LI>Ten SDKs</LI>  
<LI>Great Internet Apps</LI>  
</UL>  
</BODY>  
</HTML>  
```  
  
 Etiketler, öznitelikleri ve uzantıları tam bir açıklaması için Köprü Metni Biçimlendirme Dili (HTML) belirtime bakın:  
  
 [http://www.w3.org/pub/WWW/MarkUp/](http://www.w3.org/pub/www/markup/)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)

