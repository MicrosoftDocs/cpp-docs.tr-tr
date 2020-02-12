---
title: Bellek Yönetimi İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: aa1951211283ddf7e4823a920d5cdf19bd6d977d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141837"
---
# <a name="memory-management-functions"></a>Bellek Yönetimi İşlevleri

Bu belgede, Eşzamanlılık Çalışma Zamanı için sağlanan bellek yönetimi işlevleri, eşzamanlı bir şekilde bellek ayırmayı ve serbest getirmenize yardımcı olur.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar ve bu nedenle uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

Eşzamanlılık Çalışma Zamanı, bellek bloklarını eşzamanlı olarak ayırmak ve serbest bırakma için optimize edilmiş iki bellek yönetim işlevi sağlar. [Concurrency:: ayırma](reference/concurrency-namespace-functions.md#alloc) işlevi, belirtilen boyutu kullanarak bir bellek bloğu ayırır. [Concurrency:: Free](reference/concurrency-namespace-functions.md#free) işlevi, `Alloc`tarafından ayrılan belleği serbest bırakır.

> [!NOTE]
> `Alloc` ve `Free` işlevleri birbirine bağlıdır. `Free` işlevini yalnızca `Alloc` işlevini kullanarak ayırdığınız belleği serbest bırakmak için kullanın. Ayrıca, bellek ayırmak için `Alloc` işlevini kullandığınızda, bu belleği serbest bırakmak için yalnızca `Free` işlevini kullanın.

Farklı iş parçacıklarından veya görevlerden sabit bir ayırma boyutları kümesi ayırdığınızda ve serbest bırakırsanız `Alloc` ve `Free` işlevlerini kullanın. Eşzamanlılık Çalışma Zamanı, C çalışma zamanı yığınından ayırdığı belleği önbelleğe alır. Eşzamanlılık Çalışma Zamanı çalışan her iş parçacığı için ayrı bir bellek önbelleği barındırır; Bu nedenle, çalışma zamanı, kilitleri veya bellek engelleri kullanımı olmadan belleği yönetir. Bir uygulama, bellek önbelleğine daha sık erişildiğinde `Alloc` ve `Free` işlevlerinden daha fazla avantaj sağlar. Örneğin, `Alloc` ve `Free` genellikle `Alloc` veya `Free`çağıran bir iş parçacığından daha fazla faydalanan bir iş parçacığı.

> [!NOTE]
> Bu bellek yönetimi işlevlerini kullandığınızda ve uygulamanız çok miktarda bellek kullanıyorsa, uygulama beklediğinizden daha önce düşük bellek koşulu girebilir. Bir iş parçacığı tarafından önbelleğe alınan bellek blokları başka bir iş parçacığı tarafından kullanılamadığından, bir iş parçacığı çok miktarda bellek barındırıyorsa bu bellek kullanılabilir değildir.

## <a name="example"></a>Örnek

Bellek performansını artırmak için `Alloc` ve `Free` işlevlerini kullanan bir örnek için bkz. [nasıl yapılır: bellek performansını artırmak Için ayırma ve serbest kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
