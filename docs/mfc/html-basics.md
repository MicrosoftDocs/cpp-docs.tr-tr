---
title: HTML Temelleri
ms.date: 11/04/2016
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
ms.openlocfilehash: 63a866786abc3b1eaa87a06492b43b1c9e354882
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278391"
---
# <a name="html-basics"></a>HTML Temelleri

Çoğu tarayıcısı HTML kaynağını göz sayfaları İnceleme özelliğine sahip. HTML (Köprü Metni İşaretleme Dili) etiket sayısı göreceğiniz kaynak görüntülediğinizde, açılı ayraçlar (<>) metin ile interspersed çevrelenerek.

Aşağıdaki adımlar, basit bir Web sayfası oluşturmak için HTML etiketlerini kullanın. Bu adımlarda, Defteri'nde dosyasına düz metin yazın, birkaç değişiklik, dosyayı kaydedin ve yaptığınız değişiklikleri görmek için tarayıcıda, sayfayı yeniden yükleyin.

#### <a name="to-create-an-html-file"></a>Bir HTML dosyası oluşturmak için

1. Not Defteri'ni veya herhangi bir düz metin Düzenleyicisi'ni açın.

1. Gelen **dosya** menüsünde seçin **yeni**.

1. Aşağıdaki satırları yazın:

```
<HTML>
<HEAD>
<TITLE>Top HTML Tags</TITLE>
</HEAD>
</HTML>
```

1. Gelen **dosya** menüsünde seçin **Kaydet**ve dosyayı c:\webpages\First.htm kaydedin. Dosya düzenleyicide açık bırakın.

1. Gelen ve tarayıcınız, anahtar **dosya** menüsünde seçin **açık**, veya tür *file://C:/webpages/first.htm* tarayıcının URL'si düzenleme kutusuna. Pencere başlığı "Üst HTML etiketleri" ile boş bir sayfa görmeniz gerekir

   Etiketler halindedir ve köşeli ayraçlar içine dahil dikkat edin. Etiketler büyük küçük harfe duyarlı değildir, ancak büyük/küçük harf genellikle göze etiketleri oluşturmak için kullanılır.

   Etiket \<HTML > belge ve etiket başlar \</HTML > Bu da sona erer. Bitiş etiketleri (her zaman gerekli değil) başlangıç etiketi ile aynıdır, ancak bir eğik çizgi (/) etiketi önünde sahip. Açılı ayraç (<) ve etiket alanınızda başlangıcı arasındaki boşluk olmamalıdır.

1. Anahtarı not defteri dönün ve sonra  \< /HEAD > Satır, yazın:

```
<BODY>
    HTML is swell.
    Life is good.
</BODY>
```

1. Gelen **dosya** menüsünde seçin **Kaydet**.

1. Tarayıcıya geri dönün ve sayfayı yenileyin.

   Sözcükler, tarayıcı penceresinin istemci alanında görünür. Satır başı göz ardı edilir dikkat edin. Satır sonu isterseniz içermelidir bir `<BR>` ilk satırdan etiketi.

   Herhangi bir yere arasına metin Ekle, takip tüm adımlar için \<GÖVDESİ > ve  \< /BODY > belgenizin gövdesine eklenecek.

9. Bir üst bilgisi ekleyin:

```
<H3>Here's the big picture</H3>
```

10. Sayfanız aynı dizine kaydedilen .gif dosya kullanarak görüntü, ekleyin:

```
<IMG src="yourfile.gif">
```

11. Bir listeye ekleyin:

```
<UL>Make me an unordered list.
<LI>One programmer</LI>
<LI>Ten SDKs</LI>
<LI>Great Internet Apps</LI>
</UL>
```

12. Bunun yerine listenin sayı, kullanın eşleştirilmiş \<OL > ve \</OL > etiketleri yerine \<UL > ve \</UL > etiketleri.

Başlamanıza yardımcı olmak. Bir Web sayfasında harika bir özellik görürseniz, HTML kaynağını inceleyerek oluşturulma kullanıma bulabilirsiniz. HTML düzenleyicisi Microsoft ön sayfa gibi hem basit hem de Gelişmiş sayfaları oluşturmak için kullanılabilir.

Tüm HTML kaynak oluşturmakta dosya için şu şekildedir:

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

Etiketler, öznitelikleri ve uzantıları eksiksiz bir açıklaması için köprü metni işaretleme dili (HTML) belirtime bakın:

[En son yayımlanan sürümünü HTML](https://www.w3.org/TR/html/) W3C.org konumunda.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)
