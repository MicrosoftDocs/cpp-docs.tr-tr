---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4121'
title: Derleyici Uyarısı (düzey 4) C4121
ms.date: 11/04/2016
f1_keywords:
- C4121
helpviewer_keywords:
- C4121
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
ms.openlocfilehash: 7639bb6f5905fd1fdb782770feccf03b69d594b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261963"
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

- Paket boyutunu, uyarıya yol açan üyenin boyutuna veya daha büyük boyuta getirin. Örneğin, bu kod parçacığında, `pack(2)` veya olarak değiştirin `pack(4)` `pack(8)` .

- Üye bildirimlerini büyükten küçüğe doğru boyuta göre yeniden sıralayın. Kod parçacığında, üyenin üye olduğu gibi yapı üyelerinin sırasını ters çevirin **`long long`** **`int`** ve öğesinden **`int`** önce gelir **`char`** .

Bu uyarı, yalnızca, derleyici veri üyelerinin önüne doldurma eklerse meydana gelir. Paketleme verileri veri türüyle hizalanmamış olan bir bellek konumuna yerleştirdiğinde ve veri üyesinin önüne doldurma eklenmediğinde oluşmaz. Veri, veri boyutunun katları olan sınırlarla hizalanmadığında performans düşebilir. Hizalanmamış verilerin okunması ve yazılması, bazı mimarilerde işlemci hatalarına neden olabilir ve bu hataların çözülmesi iki veya üç kat daha fazla zaman alabilir. Hizalanmamış veri erişimleri bazı RISC mimarilerine taşınamaz.

Yapı hizalamasını belirtmek için [#pragma Pack](../../preprocessor/pack.md) veya [/ZP](../../build/reference/zp-struct-member-alignment.md) kullanabilirsiniz. ( **/ZP1** belirtildiğinde derleyici bu uyarıyı oluşturmaz.)
