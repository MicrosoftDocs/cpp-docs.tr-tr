---
title: NMAKE Önemli Hatası U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 3b1df28e3cd7b27a9e7a130d9d71c1af68db9aec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324369"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE Önemli Hatası U1033

sözdizimi hatası: 'string' beklenmeyen

Dize geçerli bir derleme görevleri dosyası sözdizimi bir parçası değil.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Kapanış açılı ayraçlar ayarlarsanız (**<<**) bir satırın başında bir satır içi dosyası için aşağıdaki hata oluşur:

    ```
    syntax error : 'EOF' unexpected
    ```

1. Derleme görevleri dosyası Makro tanımında bir eşittir işareti bulunan varsa (**=**) bir önceki adı veya ad tanımlanan hiçbir öğeye genişletilmez bir makro ise olmadan aşağıdaki hata oluşur:

    ```
    syntax error : '=' unexpected
    ```

1. Noktalı virgül (**;**) bir açıklama satırı araçları. INI satırın başında aşağıdaki hata oluşur değil:

    ```
    syntax error : ';' unexpected
    ```

1. Derleme görevleri dosyası bir sözcük işlemcisi tarafından biçimlendirilmiş, şu hata ortaya çıkabilir:

    ```
    syntax error : ':' unexpected
    ```