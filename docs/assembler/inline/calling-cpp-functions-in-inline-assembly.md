---
title: Satır içi derlemede C++ işlevlerini çağırma | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4717ae24dc1a0b6f51f7a00f68f6569c2f988c65
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678950"
---
# <a name="calling-c-functions-in-inline-assembly"></a>Satır İçi Derlemede C++ İşlevlerini Çağırma

**Microsoft'a özgü**

Bir `__asm` blok yalnızca aşırı yüklenmemiş genel C++ işlevleri çağırabilir. Aşırı yüklenmiş bir genel C++ işlev veya C++ üye işlevini çağırın, derleyici bir hata verir.

Bildirilen tüm işlevleri de çağırabilirsiniz **extern "C"** bağlantı. Böylece bir `__asm` bloğu içinde tüm standart üst bilgi dosyaları için kitaplık işlevleri bildirdiğinizden C Kitaplık işlevleri çağırmak için bir C++ programını **extern "C"** bağlantı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>