---
title: NMAKE önemli hatası U1033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1033
dev_langs:
- C++
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7492e5fd77f8e88b2191174f84c298c6166d8d89
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066391"
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