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
ms.openlocfilehash: d60ae52225ddd993c1768d0b5ce1989ab0192e45
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275395"
---
# <a name="handlers-for-standard-windows-messages"></a>Standart Windows İletileri İşleyicileri

Varsayılan standart Windows iletileri işleyicileri (**WM_**) sınıfta tanımlanmış `CWnd`. Sınıf kitaplığı, ileti adına adları bu işleyiciler için temel alır. Örneğin, işleyici için **WM_PAINT** ileti içinde bildirilmiş `CWnd` olarak:

`afx_msg void OnPaint();`

**Afx_msg** anahtar sözcüğü C++ etkisini önerir **sanal** işleyicileri diğerinden ayırt etme tarafından anahtar sözcüğü `CWnd` üye işlevleri. Ancak, bu işlevler gerçekte sanal olmadığına dikkat edin; Bunlar, bunun yerine ileti eşlemeleri uygulanır. İleti eşlemeleri yalnızca C++ dili için herhangi bir uzantısı değil, standart Önişlemci makroları bağlıdır. **Afx_msg** anahtar sözcüğü, ön işleme sonra boşluk olarak çözer.

Bir temel sınıfta tanımlanan bir işleyici geçersiz kılmak için yalnızca aynı prototipe sahip bir işlev, türetilmiş sınıf içinde ve bir ileti eşleme girdisi işleyicisini oluşturmak için tanımlar. İşleyicinizi ", sınıfın temel sınıflarında birinde aynı ada sahip herhangi bir işleyici geçersiz kılar".

Bazı durumlarda, Windows ve temel sınıfları iletide çalışabilir, böylece işleyicinizi geçersiz kılınan işleyici temel sınıfta çağırmanız gerekir. Temel sınıf işleyici geçersiz kılmada çağırdığınız koşullara bağlıdır. Bazen temel sınıf işleyici çağırın ve bazen son gerekir. İleti kendiniz işlememesi seçerseniz bazen temel sınıf işleyici, çağırırsınız. Bazen temel sınıf işleyicisi çağırma ardından değeri veya temel sınıf işleyici tarafından döndürülen durum bağlı olarak, kendi işleyici kodu koşullu olarak yürütme.

> [!CAUTION]
>  Bir temel sınıf işleyici geçirileceğini düşünüyorsanız bir işleyicisine geçirilen bağımsız değişkenler değiştirmek güvenli değildir. Örneğin, değişiklik isteği duyabilirsiniz *nChar* bağımsız değişkeni `OnChar` işleyici (büyük harfe dönüştürmek için örneğin). Bu davranış oldukça belirsiz olduğu halde bu efekti gerçekleştirmek ihtiyacınız varsa `CWnd` üye işlevi `SendMessage` yerine.

Nasıl Özellikler penceresinde belirli bir ileti işleyicisi işlevi çatısında önizlememiz yazdığında belirli bir ileti geçersiz kılmak için uygun şekilde belirlediğiniz — bir `OnCreate` işleyicisi **WM_CREATE**, örneğin — bunu biçiminde çizimler Önerilen geçersiz kılınan üye işlevi. Aşağıdaki örnek işleyici ilk temel sınıf işleyicisi çağırma ve yalnızca -1 döndürmeyen koşuluyla devam önerir.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

Kural olarak, bu işleyiciler adlarını ön ekine sahip "." Başlangıç tarihi Diğer birçok alırken bazı bu işleyiciler, bağımsız değişken almaz. Ayrıca bir dönüş türü dışındaki sahip **void**. Tüm varsayılan işleyicileri **WM_** iletileri belgelenir *MFC başvurusu* sınıfın üye işlevleri olarak `CWnd` başlamak, adları "On ile." Üye işlevi bildirimlerinde `CWnd` ön eki **afx_msg**.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
