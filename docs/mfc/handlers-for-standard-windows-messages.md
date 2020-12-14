---
description: 'Daha fazla bilgi edinin: standart Windows Iletileri için Işleyiciler'
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
ms.openlocfilehash: 161e4d85e702972ee178e2fe82aa2371f0560068
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248937"
---
# <a name="handlers-for-standard-windows-messages"></a>Standart Windows İletileri İşleyicileri

Standart Windows iletileri (**WM_**) için varsayılan işleyiciler sınıfında önceden tanımlanmıştır `CWnd` . Sınıf kitaplığı bu işleyicilerin adlarını ileti adında temel alır. Örneğin, **WM_PAINT** iletinin işleyicisi `CWnd` şöyle olarak bildirilmiştir:

`afx_msg void OnPaint();`

**Afx_msg** anahtar sözcüğü, **`virtual`** diğer üye işlevlerinden Işleyicileri ayırt ederek C++ anahtar sözcüğünün etkisini önerir `CWnd` . Ancak, bu işlevlerin gerçekten sanal olmadığına not edin; Bunlar bunun yerine ileti haritaları aracılığıyla uygulanır. İleti haritaları, C++ dilinin uzantılarına değil yalnızca standart Önişlemci makrolarına bağımlıdır. **Afx_msg** anahtar sözcüğü, ön işlemden sonra boşluk olarak çözümlenmektedir.

Temel sınıfta tanımlanan bir işleyiciyi geçersiz kılmak için, türetilmiş sınıfınıza aynı prototipi içeren bir işlev tanımlamanız ve işleyici için bir ileti eşleme girişi yapmanız yeterlidir. İşleyiciniz, sınıfınızın temel sınıflarından birinde aynı ada sahip herhangi bir işleyiciyi geçersiz kılar.

Bazı durumlarda işleyiciniz temel sınıfta geçersiz kılınan işleyiciyi çağırmalıdır, böylece temel sınıf (ler) ve Windows ileti üzerinde çalışabilir. Geçersiz kılmada temel sınıf işleyicisini çağırdığınızda, koşullara göre değişir. Bazen temel sınıf işleyicisini önce ve bazen son olarak çağırmanız gerekir. Bazen iletiyi kendiniz işleyememesi tercih ediyorsanız, temel sınıf işleyicisini koşullu olarak çağırabilirsiniz. Bazen temel sınıf işleyicisini çağırmanız ve temel sınıf işleyici tarafından döndürülen değere veya duruma bağlı olarak kendi işleyici kodunuzu koşullu olarak yürütmeniz gerekir.

> [!CAUTION]
> Bir temel sınıf işleyicisine geçirmek istiyorsanız, bir işleyiciye geçirilen bağımsız değişkenlerin değiştirilmesi güvenli değildir. Örneğin, işleyicinin *nchar* bağımsız değişkenini `OnChar` (örneğin, büyük harfe dönüştürülecek şekilde) değiştirmeyi düşünebilirsiniz. Bu davranış oldukça gizdir, ancak bu etkiyi gerçekleştirmeniz gerekiyorsa, `CWnd` bunun yerine Member işlevini kullanın `SendMessage` .

[Sınıf Sihirbazı](reference/mfc-class-wizard.md) belirli bir ileti için işleyici işlevinin iskelet 'i (WM_CREATE için bir işleyici) yazdığında, belirli bir iletiyi geçersiz kılmak için uygun şekilde nasıl belirlenir `OnCreate` , örneğin, önerilen geçersiz kılınan üye işlev biçiminde bir taslak oluşturur. Aşağıdaki örnek, işleyicinin temel sınıf işleyicisini ilk kez çağırmasını ve yalnızca-1 döndürmediğinden önce devam etmesini önerir.

[!code-cpp[NVC_MFCMessageHandling#3](codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

Kurala göre, bu işleyicilerin adları "açık" önekiyle başlar. Bu işleyicilerden bazıları bağımsız değişken almaz, diğerleri birkaç işlem sürer. Bazıları dışında bir dönüş türüne de sahiptir **`void`** . Tüm **WM_** iletiler için varsayılan Işleyiciler *MFC başvurusunda* `CWnd` adı "on" ile başlayan sınıfın üye işlevleri olarak belgelenmiştir. İçindeki üye işlev bildirimlerine `CWnd` **afx_msg** ön eki eklenir.

## <a name="see-also"></a>Ayrıca bkz.

[Ileti Işleyici Işlevlerini bildirme](declaring-message-handler-functions.md)
