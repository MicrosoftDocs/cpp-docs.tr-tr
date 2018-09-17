---
title: CL dosya adı sözdizimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04d82be73f2e73a24daeabd6219abdeadcb4cbbf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716891"
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi

CL dosya FAT, HPFS veya NTFS adlandırma kurallarına uygun adlarla kabul eder. Herhangi bir dosya adının, tam veya kısmi bir yol dahil edebilirsiniz. Tam yol, bir sürücü adı ve bir veya daha fazla dizin adlarını içerir. CL kabul dosya adları ters eğik çizgi ile ayrılmış (\\) veya İleri eğik çizgi (/). Boşluk içeren dosya adlarını karakter çift tırnak işareti içine alınmalıdır. Kısmi bir yolu, geçerli bir sürücüsü olmasını CL varsayar sürücü adı atlar. Bir yol belirtmezseniz, CL dosya geçerli dizinde olduğu varsayılır.

Dosya adı uzantısı dosyaları nasıl işleneceğini belirler. Uzantı .c, .cxx veya .cpp sahip, C ve C++ dosyaları derlenir. .Obj dosyaları, kitaplık (.lib) ve modül-tanımlama (.def) dosyaları gibi diğer dosyalar için bağlayıcı işlenen olmadan geçirilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)