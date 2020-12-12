---
description: 'Hakkında daha fazla bilgi edinin: NMAKE önemli hatası U1033'
title: NMAKE Önemli Hatası U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: e616e98a21c92137fab4b167318a9305a2175bb2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272142"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE Önemli Hatası U1033

sözdizimi hatası: ' String ' beklenmiyor

Dize, derleme görevleri dosyası için geçerli sözdiziminin bir parçası değil.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Satır içi dosyanın açılı ayraç () kapanış kümesi **<<** bir satırın başlangıcında yoksa, aşağıdaki hata oluşur:

    ```
    syntax error : 'EOF' unexpected
    ```

1. Derleme görevleri dosyasında bir makro tanımı, **=** önceki adı olmayan eşittir işareti () içeriyorsa veya tanımlanmakta olan ad hiçbir şey Nothing olarak genişleyen bir makrose aşağıdaki hata oluşur:

    ```
    syntax error : '=' unexpected
    ```

1. TOOLS.INI bir yorum satırındaki noktalı virgül (**;**) satırın başlangıcında yoksa, aşağıdaki hata oluşur:

    ```
    syntax error : ';' unexpected
    ```

1. Derleme görevleri dosyası bir sözcük işlemcisi tarafından biçimlendirildiyse aşağıdaki hata oluşabilir:

    ```
    syntax error : ':' unexpected
    ```
