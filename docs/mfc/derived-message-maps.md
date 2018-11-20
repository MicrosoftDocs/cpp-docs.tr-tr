---
title: Türetilen İleti Eşlemeleri
ms.date: 11/19/2018
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
ms.openlocfilehash: 2ae536a53a43472a4fb81d30e685fbc3faaa603f
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175612"
---
# <a name="derived-message-maps"></a>Türetilen İleti Eşlemeleri

İşleme, bir sınıfın kendi ileti denetimi ileti sırasında harita ileti eşleme hikayeyi sonuna değil. Ne olur sınıfı `CMyView` (türetilen `CView`) sahip bir ileti için eşleşen giriş yok

Aklınızda `CView`, temel sınıfını `CMyView`, sırayla türetilmiş `CWnd`. Bu nedenle `CMyView` *olduğu* bir `CView` ve *olduğu* bir `CWnd`. Bu sınıfların her birinin kendi ileti eşlemesi var. "A hiyerarşisini görüntüle" Aşağıdaki sınıfların keep ancak hiyerarşi ilişkisi gösteren şekil aklınızda bir `CMyView` nesnedir tüm üç sınıf özelliklere sahip tek bir nesne.

![Görünüm hiyerarşisini](../mfc/media/vc38621.gif "görünüm hiyerarşisi") <br/>
Hiyerarşisini görüntüle

Böyle bir ileti sınıfı eşleştirilemiyor `CMyView`'s ileti eşlemesi, framework hemen kendi taban sınıfının ileti eşlemesi de arar. `BEGIN_MESSAGE_MAP` Makrosu ileti eşlemede başlangıcında, bağımsız değişkenler olarak iki sınıf adlarını belirtir:

[!code-cpp[NVC_MFCMessageHandling#2](../mfc/codesnippet/cpp/derived-message-maps_1.cpp)]

İlk bağımsız değişken ileti eşlemesi ait olduğu sınıfın adı. İkinci bağımsız değişkeni hemen temel sınıf ile bir bağlantı sağlar — `CView` burada — framework kendi ileti eşlemesi çok arama yapabilirsiniz.

Bir temel sınıfta sağlanan ileti işleyicileri, bu nedenle türetilmiş sınıf tarafından devralınır. Tüm işleyici üye işlevleri sanal yapmaya gerek kalmadan bu normal sanal üye işleve çok benzer.

İletinin varsayılan işleme, işleyici yok herhangi bir temel sınıf ileti eşlemeleri bulunursa gerçekleştirilir. Bir komut iletisiyse framework sonraki komut hedefe yönlendirir. Standart bir Windows ileti ise, ileti için uygun bir varsayılan pencere yordamını geçirilir.

İleti eşleme eşleşen hızlandırmak için aynı ileti yeniden alacağını olasılığı son eşleşmeleri ile framework önbelleğe alır. Bunun bir sonucu framework işlemleri iletileri oldukça etkili bir şekilde işlenmemiş ' dir. İleti eşlemeleri de alanı-sanal işlevler kullanan uygulamalar verimlidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'ün İleti Eşlemelerini Araması](../mfc/how-the-framework-searches-message-maps.md)

