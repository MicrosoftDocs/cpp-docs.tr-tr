---
title: Derleyici Uyarısı (düzey 4) C4121 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4121
dev_langs:
- C++
helpviewer_keywords:
- C4121
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1cda66d120278034fc8c19ba0221be047a75eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293293"
---
# <a name="compiler-warning-level-4-c4121"></a>Derleyici Uyarısı (düzey 4) C4121
'sembol': bir üyenin hizalaması paketlemeye duyarlıydı  
  
 Derleyici, bir yapı üyesini paket sınırında hizalamak için doldurma ekledi ancak paket değeri üyenin boyutundan daha az. Örneğin, aşağıdaki kod parçacığı C4121 oluşturur:  
  
```  
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
  
-   Paket boyutunu, uyarıya yol açan üyenin boyutuna veya daha büyük boyuta getirin. Örneğin, bu parçasında değiştirme `pack(2)` için `pack(4)` veya `pack(8)`.  
  
-   Üye bildirimlerini büyükten küçüğe doğru boyuta göre yeniden sıralayın. Kod parçacığında, Yapı üyeleri sırasını tersine çevirmek şekilde `long long` üye önündeki `int`ve `int` önündeki `char`.  
  
 Bu uyarı, yalnızca, derleyici veri üyelerinin önüne doldurma eklerse meydana gelir. Paketleme verileri veri türüyle hizalanmamış olan bir bellek konumuna yerleştirdiğinde ve veri üyesinin önüne doldurma eklenmediğinde oluşmaz. Veri, veri boyutunun katları olan sınırlarla hizalanmadığında performans düşebilir. Hizalanmamış verilerin okunması ve yazılması, bazı mimarilerde işlemci hatalarına neden olabilir ve bu hataların çözülmesi iki veya üç kat daha fazla zaman alabilir. Hizalanmamış veri erişimleri bazı RISC mimarilerine taşınamaz.  
  
 Kullanabileceğiniz [#pragma paketi](../../preprocessor/pack.md) veya [/Zp](../../build/reference/zp-struct-member-alignment.md) yapı hizalama belirtmek için. (Derleyici olduğunda bu uyarı oluşturmaz **/Zp1** belirtilir.)