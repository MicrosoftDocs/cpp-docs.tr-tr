---
description: 'Daha fazla bilgi edinin: bellek yönetimi Işlevleri'
title: Bellek Yönetimi İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- memory management functions [Concurrency Runtime]
ms.assetid: d303dd2a-dfa4-4d90-a508-f6aa290bb9ea
ms.openlocfilehash: d75778f99294c1a177ac204bb0fb96c3ee84422c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205544"
---
# <a name="memory-management-functions"></a>Bellek Yönetimi İşlevleri

Bu belgede, Eşzamanlılık Çalışma Zamanı için sağlanan bellek yönetimi işlevleri, eşzamanlı bir şekilde bellek ayırmayı ve serbest getirmenize yardımcı olur.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar ve bu nedenle uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

Eşzamanlılık Çalışma Zamanı, bellek bloklarını eşzamanlı olarak ayırmak ve serbest bırakma için optimize edilmiş iki bellek yönetim işlevi sağlar. [Concurrency:: ayırma](reference/concurrency-namespace-functions.md#alloc) işlevi, belirtilen boyutu kullanarak bir bellek bloğu ayırır. [Concurrency:: Free](reference/concurrency-namespace-functions.md#free) işlevi tarafından ayrılan belleği serbest bırakır `Alloc` .

> [!NOTE]
> `Alloc`Ve `Free` işlevleri birbirlerine bağımlıdır. İşlevini `Free` yalnızca işlevini kullanarak ayırdığınız belleği serbest bırakmak için kullanın `Alloc` . Ayrıca, `Alloc` bellek ayırmak için işlevini kullandığınızda `Free` bu belleği serbest bırakmak için yalnızca işlevini kullanın.

`Alloc` `Free` Farklı iş parçacıklarından veya görevlerden sabit bir ayırma boyutları kümesi tahsis ve serbest bırakma yaptığınızda ve işlevlerini kullanın. Eşzamanlılık Çalışma Zamanı, C çalışma zamanı yığınından ayırdığı belleği önbelleğe alır. Eşzamanlılık Çalışma Zamanı çalışan her iş parçacığı için ayrı bir bellek önbelleği barındırır; Bu nedenle, çalışma zamanı, kilitleri veya bellek engelleri kullanımı olmadan belleği yönetir. Bir uygulama, `Alloc` `Free` bellek önbelleğine daha sık erişildiğinde ve işlevlerinden daha fazla avantaj sağlar. Örneğin, her ikisini de çağıran bir iş parçacığı `Alloc` ve `Free` öncelikle veya çağıran bir iş parçacığından daha fazlasını `Alloc` sağlar `Free` .

> [!NOTE]
> Bu bellek yönetimi işlevlerini kullandığınızda ve uygulamanız çok miktarda bellek kullanıyorsa, uygulama beklediğinizden daha önce düşük bellek koşulu girebilir. Bir iş parçacığı tarafından önbelleğe alınan bellek blokları başka bir iş parçacığı tarafından kullanılamadığından, bir iş parçacığı çok miktarda bellek barındırıyorsa bu bellek kullanılabilir değildir.

## <a name="example"></a>Örnek

`Alloc` `Free` Bellek performansını artırmak için ve işlevlerini kullanan bir örnek için bkz. [nasıl yapılır: bellek performansını artırmak Için ayırma ve serbest kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: bellek performansını artırmak için ayırma ve serbest kullanma](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)
