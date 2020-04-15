---
title: HTML Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: 6d3a692eab47a1309ee0248b51ab8563fb077d5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377243"
---
# <a name="html-basics"></a>HTML Temelleri

Çoğu tarayıcı, göz atmanız sayfaların HTML kaynağını inceleme özelliğine sahiptir. Kaynağı görüntülediğinizde, metinle serpiştirilmiş açı parantezi(<>) ile çevrili bir dizi HTML (Hypertext biçimlendirme dili) etiketi görürsünüz.

Aşağıdaki adımlar, basit bir Web sayfası oluşturmak için HTML etiketlerini kullanır. Bu adımlarda, Not Defteri'ndeki bir dosyaya düz metin yazar, birkaç değişiklik yapar, dosyayı kaydeder ve sayfanızı tarayıcıda yeniden yükleyerek değişikliklerinizi görürsünüz.

#### <a name="to-create-an-html-file"></a>HTML dosyası oluşturmak için

1. Not Defteri'ni veya herhangi bir düz metin düzenleyiciyi açın.

1. **Dosya** menüsünden **Yeni'yi**seçin.

1. Aşağıdaki satırları yazın:

    ```html
    <HTML>
    <HEAD>
    <TITLE>Top HTML Tags</TITLE>
    </HEAD>
    </HTML>
    ```

1. **Dosya** menüsünden **Kaydet'i**seçin ve dosyayı c:\webpages\First.htm olarak kaydedin. Dosyayı düzenleyicide açık bırakın.

1. Tarayıcınıza geçin ve **Dosya** menüsünden **Tarayıcının**URL'si için file://C:/webpages/first.htm aç'ı seçin veya *file://C:/webpages/first.htm* yazın. Pencere başlığı "Üst HTML Etiketleri" ile boş bir sayfa görmeniz gerekir.

   Etiketlerin eşleştirilmiş ve açı braketlerine dahil olduğuna dikkat edin. Etiketler büyük/küçük harf duyarlı değildir, ancak büyük harf genellikle etiketleri öne yapmak için kullanılır.

   HTML \<etiketi> belgeyi başlatır \<ve /HTML> etiketi belgeyi sona erdirer. Bitiş etiketleri (her zaman gerekli değildir) başlangıç etiketiyle aynıdır, ancak etiketin önünde ileri eğik çizgi (/) bulunur. Açı braketi (<) ile etiketinizin başlangıcı arasında boşluk olmamalıdır.

1. Not Defteri'ne geri dön \<ve /HEAD> satırından sonra şunları yazın:

    ```html
    <BODY>
        HTML is swell.
        Life is good.
    </BODY>
    ```

1. **Dosya** menüsünden **Kaydet'i**seçin.

1. Tarayıcınıza geri dön ve sayfayı yenileyin.

   Sözcükler tarayıcınızın penceresinin istemci alanında görünür. Taşıma nızın geri dönüşügöz ardı edilir dikkat edin. Satır sonu istiyorsanız, ilk satırdan sonra `<BR>` bir etiket eklemeniz gerekir.

   İzleyen tüm adımlar için, belgenizin \<gövdesine \<eklemek için METNI BODY> ve /BODY> arasına ekleyin.

1. Üstbilgi ekleyin:

    ```html
    <H3>Here's the big picture</H3>
    ```

1. Sayfanızla aynı dizinde kaydedilmiş bir .gif dosyasını kullanarak bir resim ekleyin:

    ```html
    <IMG src="yourfile.gif">
    ```

1. Liste ekle:

    ```html
    <UL>Make me an unordered list.
    <LI>One programmer</LI>
    <LI>Ten SDKs</LI>
    <LI>Great Internet Apps</LI>
    </UL>
    ```

1. Bunun yerine listeyi \<numaralandırmak \< \<için, UL> ve /UL \<> etiketleri yerine eşleştirilmiş OL> ve /OL> etiketleri kullanın.

Bu seni işe bular. Bir Web sayfasında harika bir özellik görürseniz, HTML kaynağını inceleyerek nasıl oluşturulduğunu öğrenebilirsiniz. Microsoft Front Page gibi HTML düzenleyicileri hem basit hem de gelişmiş sayfalar oluşturmak için kullanılabilir.

Oluşturmakta olduğunuz dosyanın tüm HTML kaynağı aşağıda verilmiştir:

```html
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

Etiketlerin, özniteliklerin ve uzantıların tam açıklaması için, Hypertext Markup Language (HTML) belirtimine bakın:

[W3C.org'da HTML'nin en son yayınlanan sürümü.](https://www.w3.org/TR/html/)

## <a name="see-also"></a>Ayrıca bkz.

[MFC İnternet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)
