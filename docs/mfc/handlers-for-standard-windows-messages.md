---
title: Standart Windows İletileri İşleyicileri
ms.date: 11/04/2016
f1_keywords:
- afx_msg
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
ms.openlocfilehash: 9a136caf3a1d22151cb9cfd48e1cd3f999ab51ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370495"
---
# <a name="handlers-for-standard-windows-messages"></a>Standart Windows İletileri İşleyicileri

Standart Windows iletileri **(WM_)** için varsayılan işleyicileri sınıfta `CWnd`önceden tanımlanır. Sınıf kitaplığı, ileti adına bu işleyicilerin adlarını temel adatır. Örneğin, **WM_PAINT** iletisinin işleyicisi `CWnd` aşağıdaki şekilde bildirilir:

`afx_msg void OnPaint();`

**afx_msg** anahtar kelimesi, işleyicileri **virtual** diğer `CWnd` üye işlevlerden ayırarak C++ sanal anahtar kelimesinin etkisini önerir. Ancak, bu işlevlerin aslında sanal olmadığını unutmayın; bunun yerine ileti haritaları aracılığıyla uygulanır. İleti eşlemleri yalnızca standart önişlemci makrolarına bağlıdır, C++ dilinin uzantılarına değil. anahtar kelime **nin afx_msg,** ön işleme den sonra beyaz alana gider.

Taban sınıfta tanımlanan bir işleyiciyi geçersiz kılmak için, türemiş sınıfınızda aynı prototipe sahip bir işlev tanımlayın ve işleyici için bir ileti eşlemi girişi yapın. İşleyiciniz, sınıfınızın temel sınıflarından herhangi birinde aynı adı taşıyan herhangi bir işleyiciyi "geçersiz kılar".

Bazı durumlarda, işleyiciniz taban sınıf(es) ve Windows'un iletiüzerinde çalışabilmesi için alt sınıftaki geçersiz kılınan işleyiciyi çağırmalıdır. Geçersiz kılmada taban sınıf işleyiciyi çağırdığınız yer koşullara bağlıdır. Bazen taban sınıf işleyicisini ilk ve bazen son olarak aramanız gerekir. İletiyi kendiniz işlememeyi seçerseniz, bazen taban sınıf işleyicisini koşullu olarak çağırırsınız. Bazen taban sınıf işleyicisini aramalı, ardından taban sınıf işleyicisi tarafından döndürülen değer e veya duruma bağlı olarak kendi işleyici kodunuzu koşullu olarak çalıştırmalısınız.

> [!CAUTION]
> Bir taban sınıf işleyicisine geçirmek niyetindeyseniz, işleyiciye geçirilen bağımsız değişkenleri değiştirmek güvenli değildir. Örneğin, `OnChar` işleyicinin *nChar* bağımsız değişkenini değiştirmek isteyebilirsiniz (örneğin büyük harfe dönüştürmek için). Bu davranış oldukça belirsizdir, ancak bu etkiyi `CWnd` gerçekleştirmeniz `SendMessage` gerekiyorsa, bunun yerine üye işlevi kullanın.

Sınıf [Sihirbazı](reference/mfc-class-wizard.md) belirli bir ileti için işleyici işlevinin iskeletini yazdığında belirli bir iletiyi geçersiz kılmanın uygun yolunu nasıl belirlersiniz - örneğin `OnCreate` **WM_CREATE**için bir işleyici - önerilen geçersiz kılınan üye işlev biçiminde çizim yapar. Aşağıdaki örnek, işleyicinin önce taban sınıf işleyicisini aramasını ve yalnızca -1'i döndürmemesi koşuluyla devam etmesini önerir.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

Kural olarak, bu işleyicilerin adları "A) öneki yle başlar. Bu işleyicilerin bazıları hiçbir argüman almak, diğerleri birkaç alır. Bazıları da **boşluk**dışında bir dönüş türü var. Tüm **WM_** iletilerinin varsayılan işleyicileri *MFC Başvurusu'nda* adları "A) ile başlayan sınıfın `CWnd` üye işlevleri olarak belgelenir. Üye işlev bildirimleri `CWnd` **afx_msg**ile önceden belirlenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
