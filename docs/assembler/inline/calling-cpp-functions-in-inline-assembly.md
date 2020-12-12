---
description: 'Hakkında daha fazla bilgi edinin: satır Içi derlemede C++ Işlevlerini çağırma'
title: Satır İçi Derlemede C++ İşlevlerini Çağırma
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
ms.openlocfilehash: 3efd4f00eae5810b287a27546bba3160f479b8f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117971"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma

**Microsoft'a Özgü**

Bir **`__asm`** blok, yalnızca aşırı yüklü olmayan genel C++ işlevlerini çağırabilir. Aşırı yüklenmiş bir genel C++ işlevini veya bir C++ üye işlevini çağırırsanız, derleyici bir hata verir.

Ayrıca, **extern "C"** bağlantısıyla belirtilen işlevleri de çağırabilirsiniz. Bu, **`__asm`** tüm standart üstbilgi dosyaları kitaplık işlevlerini **extern "C"** bağlantısına sahip olacak şekilde bildirtiğinden, C++ programı Içindeki bir bloğun C kitaplığı işlevlerini çağırmasını sağlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
