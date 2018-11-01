---
title: Bellek Yönetimi İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: d8dfc8bbb200258818c38e931e978cc3be292525
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454088"
---
# <a name="memory-management-functions"></a>Bellek Yönetimi İşlevleri

Bu belgede, eşzamanlılık çalışma zamanı ayırın ve eş zamanlı bir şekilde belleği boşaltmak yardımcı olmak için bellek yönetimi işlevleri açıklanmaktadır.

> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, bir uygulama oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.

Eşzamanlılık Çalışma zamanı ayırma ve bellek blokları eş zamanlı bir şekilde boşaltmak için optimize edilmiş iki bellek yönetimi işlevleri sağlar. [Concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) işlevi, belirtilen boyut kullanarak bir bellek bloğu ayırır. [Concurrency::Free](reference/concurrency-namespace-functions.md#free) işlevi tarafından ayrılan bellek serbest bırakma `Alloc`.

> [!NOTE]
>  `Alloc` Ve `Free` işlevleri birbirine dayanır. Kullanım `Free` işlevi yalnızca kullanarak tahsis ettiğiniz bellek serbest bırakmak için `Alloc` işlevi. Kullanırken aynı zamanda, `Alloc` bellek ayırmak için yalnızca işlev `Free` bu belleği serbest bırakmak için işlevi.

Kullanım `Alloc` ve `Free` ayırmak ve ayırma boyutları farklı iş parçacıkları veya görevleri sabit bir dizi boş olduğunda çalışır. Eşzamanlılık Çalışma zamanı, C çalışma zamanı yığından ayırır bellek önbelleğe alır. Eşzamanlılık Çalışma zamanı, her bir çalışan iş parçacığı için ayrı bir önbellek tutar; Bu nedenle, bellek kilitleri ya da belleği engelleri kullanmadan çalışma zamanı yönetir. Bir uygulama hakkında daha fazla avantaj `Alloc` ve `Free` önbellek daha sık erişilen çalışır. Örneğin, her ikisi de sık çağıran bir iş parçacığı `Alloc` ve `Free` avantajları öncelikli olarak çağıran iş parçacığı fazlasını `Alloc` veya `Free`.

> [!NOTE]
>  Bu bellek yönetimi işlevleri kullanın ve bellek, uygulama, uygulama kullanan çok sayıda girebilirsiniz bir düşük bellek durumu daha kısa süre içinde çok bekler. İş parçacığı tarafından önbelleğe alınan bellek blokları tek bir iş parçacığı büyük miktarda bellek tutuyorsa diğer herhangi bir dizi için kullanılabilir olmadığından, bu bellek kullanılabilir değil.

## <a name="example"></a>Örnek

Kullanan bir örnek için `Alloc` ve `Free` bellek performansını artırmak için işlevleri [nasıl yapılır: kullanım ayırma ve serbest bellek performansını artırmak için](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)

