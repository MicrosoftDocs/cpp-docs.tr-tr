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
ms.openlocfilehash: 4f512c3b9a7fce5cddd582fa774742d2b1ac0967
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907437"
---
# <a name="handlers-for-standard-windows-messages"></a>Standart Windows İletileri İşleyicileri

Standart Windows iletileri (**WM_** ) için varsayılan işleyiciler sınıfında `CWnd`önceden tanımlanmıştır. Sınıf kitaplığı bu işleyicilerin adlarını ileti adında temel alır. Örneğin, **WM_PAINT** iletisi için işleyici `CWnd` şöyle bildirilmiştir:

`afx_msg void OnPaint();`

**Afx_msg** anahtar sözcüğü, diğer `CWnd` üye işlevlerinden işleyicileri C++ ayırt ederek **sanal** anahtar sözcüğünün etkisini önerir. Ancak, bu işlevlerin gerçekten sanal olmadığına not edin; Bunlar bunun yerine ileti haritaları aracılığıyla uygulanır. İleti haritaları, C++ dilin uzantılarına değil yalnızca standart Önişlemci makrolarına bağımlıdır. **Afx_msg** anahtar sözcüğü, ön işlemden sonra boşluk olarak çözümlenmektedir.

Temel sınıfta tanımlanan bir işleyiciyi geçersiz kılmak için, türetilmiş sınıfınıza aynı prototipi içeren bir işlev tanımlamanız ve işleyici için bir ileti eşleme girişi yapmanız yeterlidir. İşleyiciniz, sınıfınızın temel sınıflarından birinde aynı ada sahip herhangi bir işleyiciyi geçersiz kılar.

Bazı durumlarda işleyiciniz temel sınıfta geçersiz kılınan işleyiciyi çağırmalıdır, böylece temel sınıf (ler) ve Windows ileti üzerinde çalışabilir. Geçersiz kılmada temel sınıf işleyicisini çağırdığınızda, koşullara göre değişir. Bazen temel sınıf işleyicisini önce ve bazen son olarak çağırmanız gerekir. Bazen iletiyi kendiniz işleyememesi tercih ediyorsanız, temel sınıf işleyicisini koşullu olarak çağırabilirsiniz. Bazen temel sınıf işleyicisini çağırmanız ve temel sınıf işleyici tarafından döndürülen değere veya duruma bağlı olarak kendi işleyici kodunuzu koşullu olarak yürütmeniz gerekir.

> [!CAUTION]
>  Bir temel sınıf işleyicisine geçirmek istiyorsanız, bir işleyiciye geçirilen bağımsız değişkenlerin değiştirilmesi güvenli değildir. Örneğin, `OnChar` işleyicinin *nchar* bağımsız değişkenini (örneğin, büyük harfe dönüştürülecek şekilde) değiştirmeyi düşünebilirsiniz. Bu davranış oldukça gizdir, ancak bu etkiyi gerçekleştirmeniz gerekiyorsa, bunun yerine `CWnd` member işlevini `SendMessage` kullanın.

[Sınıf Sihirbazı](reference/mfc-class-wizard.md) belirli bir ileti için işleyici işlevinin iskeçini yazdığında, örneğin `OnCreate` **WM_CREATE**için bir işleyici olan belirli bir iletiyi geçersiz kılmak için doğru şekilde nasıl belirlenir (örneğin, önerilen geçersiz kılınan üye işlevi. Aşağıdaki örnek, işleyicinin temel sınıf işleyicisini ilk kez çağırmasını ve yalnızca-1 döndürmediğinden önce devam etmesini önerir.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

Kurala göre, bu işleyicilerin adları "açık" önekiyle başlar. Bu işleyicilerden bazıları bağımsız değişken almaz, diğerleri birkaç işlem sürer. Bazıları **void**dışında bir dönüş türüne de sahiptir. Tüm **WM_** iletileri için varsayılan işleyiciler, *MFC başvurusunda* adları "on" ile başlayan sınıfın `CWnd` üye işlevleri olarak belgelenmiştir. İçindeki `CWnd` üye işlev bildirimlerinin önüne **afx_msg**eklenir.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
