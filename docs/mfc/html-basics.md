---
description: 'Daha fazla bilgi edinin: HTML temelleri'
title: HTML Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: f32926beb9152441169320bf3553b0066f78fa7c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290251"
---
# <a name="html-basics"></a>HTML Temelleri

Tarayıcıların çoğunda, gözatarken sayfaların HTML kaynağını İnceleme özelliği vardır. Kaynağı görüntülediğinizde, açılı ayraçlar (<>) ile çevrelenen ve metinle birlikte bir dizi HTML (köprü metni biçimlendirme dili) etiketi görürsünüz.

Aşağıdaki adımlar basit bir Web sayfası oluşturmak için HTML etiketlerini kullanır. Bu adımlarda, Not defteri 'nde bir dosyaya düz metin yazabilir, birkaç değişiklik yapmanız, dosyayı kaydetmeniz ve yaptığınız değişiklikleri görmek için sayfanızı tarayıcıda yeniden yüklemeniz gerekir.

#### <a name="to-create-an-html-file"></a>Bir HTML dosyası oluşturmak için

1. Not defteri 'ni veya herhangi bir düz metin düzenleyicisini açın.

1. **Dosya** menüsünde **Yeni**' yi seçin.

1. Aşağıdaki satırları yazın:

    ```html
    <HTML>
    <HEAD>
    <TITLE>Top HTML Tags</TITLE>
    </HEAD>
    </HTML>
    ```

1. **Dosya** menüsünde **Kaydet**' i seçin ve dosyayı c:\webpages\First.htm olarak kaydedin. Dosyayı düzenleyicide açık bırakın.

1. Tarayıcınıza geçiş yapın ve **Dosya** menüsünden **Aç**' ı SEÇIN veya tarayıcının URL 'si düzenleme kutusuna *File://C:/webpages/first.htm* yazın. Pencere başlığı "üst HTML etiketleri" olan boş bir sayfa görmeniz gerekir.

   Etiketlerin eşleştirildiğine ve açılı ayraçlar içine dahil edildiğini unutmayın. Etiketler büyük/küçük harfe duyarlı değildir, ancak büyük küçük harf genellikle etiketlerin öne çıkmasını sağlamak için kullanılır.

   Etiketi \<HTML> belgeyi başlatır ve etiket \</HTML> onu sonlandırır. Bitiş etiketleri (her zaman gerekli değil) başlangıç etiketiyle aynıdır, ancak etiketin önünde eğik çizgi (/) vardır. Açılı ayraç (<) ve etiketlerinizin başlangıcı arasında boşluk olmamalıdır.

1. Not defteri 'ne geri dönün ve satırdan sonra \</HEAD> şunu yazın:

    ```html
    <BODY>
        HTML is swell.
        Life is good.
    </BODY>
    ```

1. **Dosya** menüsünde **Kaydet**' i seçin.

1. Tarayıcınıza geri dönün ve sayfayı yenileyin.

   Sözcükler tarayıcınızın penceresinin istemci alanında görüntülenir. Satırlarınızın dönebildiğine dikkat edin. Satır sonu eklemek istiyorsanız, `<BR>` ilk satırdan sonra bir etiket eklemeniz gerekir.

   İzleyen tüm adımlarda, \<BODY> \</BODY> belgenizin gövdesine eklemek için ve arasında bir yere metin ekleyin.

1. Üst bilgi ekleyin:

    ```html
    <H3>Here's the big picture</H3>
    ```

1. Sayfanız ile aynı dizine kaydedilmiş bir. gif dosyası kullanarak bir resim ekleyin:

    ```html
    <IMG src="yourfile.gif">
    ```

1. Liste Ekle:

    ```html
    <UL>Make me an unordered list.
    <LI>One programmer</LI>
    <LI>Ten SDKs</LI>
    <LI>Great Internet Apps</LI>
    </UL>
    ```

1. Bunun yerine listeyi numaralandırmak için \<OL> ve etiketlerinin yerine eşleştirilmiş ve \</OL> etiketleri kullanın \<UL> \</UL> .

Bu, başlamanıza gerekir. Web sayfasında harika bir özellik görürseniz, HTML kaynağını inceleyerek nasıl oluşturulduğunu öğrenebilirsiniz. Microsoft ön sayfası gibi HTML düzenleyicileri, hem basit hem de gelişmiş sayfalar oluşturmak için kullanılabilir.

Oluşturmakta olduğunuz dosya için HTML kaynağının tamamı aşağıda verilmiştir:

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

Etiketlerin, özniteliklerin ve uzantıların ayrıntılı bir açıklaması için Köprü Metni Biçimlendirme Dili (HTML) belirtimine bakın:

W3C.org adresinde [en son yayınlanan HTML sürümü](https://www.w3.org/TR/html/) .

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Temelleri](mfc-internet-programming-basics.md)
