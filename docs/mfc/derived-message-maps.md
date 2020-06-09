---
title: Türetilen İleti Eşlemeleri
ms.date: 11/19/2018
helpviewer_keywords:
- message handling [MFC], derived message handlers
- messages, routing
- message maps [MFC], derived
- derived message maps
ms.assetid: 21829556-6e64-40c3-8279-fed85d99de77
ms.openlocfilehash: 0868b12720cfa338ab7275a358e065506adc11d1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615925"
---
# <a name="derived-message-maps"></a>Türetilen İleti Eşlemeleri

İleti işleme sırasında, bir sınıfın kendi ileti eşlemesini denetlemek ileti eşleme hikayesinin sonu değildir. Sınıfın `CMyView` (türetilmiş from `CView` ) bir ileti için eşleşen bir girişi yoksa ne olur

`CView`Öğesinin temel sınıfının `CMyView` sırasıyla türetildiğini aklınızda bulundurun `CWnd` . Bu `CMyView` *,* bir `CView` ve *is* ' dir `CWnd` . Bu sınıfların her biri kendi ileti eşlemesine sahiptir. Aşağıdaki şekil "bir görünüm hiyerarşisi" sınıfların hiyerarşik ilişkisini gösterir, ancak bir `CMyView` nesnenin üç sınıfın özelliklerine sahip tek bir nesne olduğunu aklınızda bulundurun.

![Bir görünümün hiyerarşisi](../mfc/media/vc38621.gif "Bir görünümün hiyerarşisi") <br/>
Bir görünüm hiyerarşisi

Bu nedenle, sınıfın ileti haritasında bir ileti eşleştirilemezse `CMyView` , çerçeve kendi temel sınıfının ileti haritasını da arar. `BEGIN_MESSAGE_MAP`İleti eşlemesinin başlangıcında makro, bağımsız değişkenleri olarak iki sınıf adı belirtir:

[!code-cpp[NVC_MFCMessageHandling#2](codesnippet/cpp/derived-message-maps_1.cpp)]

İlk bağımsız değişken, ileti eşlemesinin ait olduğu sınıfı adlandırır. İkinci bağımsız değişken, en hızlı temel sınıfla bir bağlantı sağlar — `CView` burada, çerçeve ileti eşlemesinde da arama yapabilir.

Bir temel sınıfta sunulan ileti işleyicileri, bu nedenle türetilmiş sınıf tarafından devralınır. Bu, tüm işleyici üye işlevlerini sanal hale getirmek gerekmeden normal sanal üye işlevlerine çok benzer.

Temel sınıf ileti eşlemlerinin hiçbirinde hiçbir işleyici bulunmazsa, varsayılan ileti işleme gerçekleştirilir. İleti bir komut ise, Framework onu bir sonraki komut hedefine yönlendirir. Standart bir Windows iletitiyse ileti, uygun varsayılan pencere yordamına geçirilir.

İleti eşleme eşleştirmesini hızlandırmak için çerçeve, en son eşleşmeleri aynı iletiyi yeniden alacak olasılığında önbelleğe alır. Bunun bir sonucu olarak, çerçeve işlenmemiş iletileri oldukça verimli bir şekilde işler. İleti haritaları Ayrıca sanal işlevleri kullanan uygulamalardan daha fazla alan sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Ileti eşlemelerini nasıl arar](how-the-framework-searches-message-maps.md)
