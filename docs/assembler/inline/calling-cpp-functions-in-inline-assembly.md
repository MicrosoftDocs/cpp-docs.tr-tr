---
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
ms.openlocfilehash: f16e466ebb5f31231411eaaf9a1a85bfcc46a34d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169584"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma

**Microsoft 'a özgü**

`__asm` bloğu yalnızca aşırı yüklü olmayan genel C++ işlevleri çağırabilir. Aşırı yüklenmiş bir genel C++ işlev veya C++ üye işlevi çağırırsanız, derleyici bir hata verir.

Ayrıca, **extern "C"** bağlantısıyla belirtilen işlevleri de çağırabilirsiniz. Bu, tüm standart üstbilgi dosyaları kitaplık C++ işlevlerini **extern "C"** bağlantısına sahip olacak şekilde bildirtiğinden, bir program içindeki `__asm` bloğunun C kitaplığı işlevlerini çağırmasını sağlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
