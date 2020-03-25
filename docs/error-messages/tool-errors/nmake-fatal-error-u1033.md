---
title: NMAKE Önemli Hatası U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: 4511b15c84479c3531a3bea85964e2768de0181f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173393"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE Önemli Hatası U1033

sözdizimi hatası: ' String ' beklenmiyor

Dize, derleme görevleri dosyası için geçerli sözdiziminin bir parçası değil.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Satır içi dosyanın açılı ayraç ( **<<** ) kapanış kümesi bir satırın başlangıcında yoksa, aşağıdaki hata oluşur:

    ```
    syntax error : 'EOF' unexpected
    ```

1. Derleme görevleri dosyasında bir makro tanımı, önceki adı olmayan bir eşittir işareti ( **=** ) içeriyorsa veya tanımlanmakta olan ad hiçbir şey Nothing olarak genişleyen bir makrose aşağıdaki hata oluşur:

    ```
    syntax error : '=' unexpected
    ```

1. ARAÇLARıNDAKI bir yorum satırında noktalı virgül ( **;** ). INI satırın başlangıcında değil, aşağıdaki hata oluşur:

    ```
    syntax error : ';' unexpected
    ```

1. Derleme görevleri dosyası bir sözcük işlemcisi tarafından biçimlendirildiyse aşağıdaki hata oluşabilir:

    ```
    syntax error : ':' unexpected
    ```
