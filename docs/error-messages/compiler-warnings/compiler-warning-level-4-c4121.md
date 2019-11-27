---
title: Derleyici Uyarısı (düzey 4) C4121
ms.date: 11/04/2016
f1_keywords:
- C4121
helpviewer_keywords:
- C4121
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
ms.openlocfilehash: bafa16cbad2cb0a2475cae5a98c608096e296442
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541616"
---
# <a name="compiler-warning-level-4-c4121"></a>Derleyici Uyarısı (düzey 4) C4121

'sembol': bir üyenin hizalaması paketlemeye duyarlıydı

Derleyici, bir yapı üyesini paket sınırında hizalamak için doldurma ekledi ancak paket değeri üyenin boyutundan daha az. Örneğin, aşağıdaki kod parçacığı C4121 oluşturur:

```cpp
// C4121.cpp
// compile with: /W4 /c
#pragma pack(2)
struct s
{
   char a;
   int b; // C4121
   long long c;
};
```

Bu sorunu gidermek için aşağıdaki değişikliklerden birini yapın:

- Paket boyutunu, uyarıya yol açan üyenin boyutuna veya daha büyük boyuta getirin. Örneğin, bu kod parçacığında `pack(2)` `pack(4)` veya `pack(8)`olarak değiştirin.

- Üye bildirimlerini büyükten küçüğe doğru boyuta göre yeniden sıralayın. Kod parçacığında, `long long` üye `int`önce `int` ve `char`önce önce yapı üyelerinin sırasını ters çevirin.

Bu uyarı, yalnızca, derleyici veri üyelerinin önüne doldurma eklerse meydana gelir. Paketleme verileri veri türüyle hizalanmamış olan bir bellek konumuna yerleştirdiğinde ve veri üyesinin önüne doldurma eklenmediğinde oluşmaz. Veri, veri boyutunun katları olan sınırlarla hizalanmadığında performans düşebilir. Hizalanmamış verilerin okunması ve yazılması, bazı mimarilerde işlemci hatalarına neden olabilir ve bu hataların çözülmesi iki veya üç kat daha fazla zaman alabilir. Hizalanmamış veri erişimleri bazı RISC mimarilerine taşınamaz.

Yapı hizalamasını belirtmek için [#pragma Pack](../../preprocessor/pack.md) veya [/ZP](../../build/reference/zp-struct-member-alignment.md) kullanabilirsiniz. ( **/ZP1** belirtildiğinde derleyici bu uyarıyı oluşturmaz.)