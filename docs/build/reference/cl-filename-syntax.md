---
title: CL Dosya Adı Sözdizimi
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: 929096ed169a33e0876c3afb68f3594757d61e4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438941"
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi

CL dosya FAT, HPFS veya NTFS adlandırma kurallarına uygun adlarla kabul eder. Herhangi bir dosya adının, tam veya kısmi bir yol dahil edebilirsiniz. Tam yol, bir sürücü adı ve bir veya daha fazla dizin adlarını içerir. CL kabul dosya adları ters eğik çizgi ile ayrılmış (\\) veya İleri eğik çizgi (/). Boşluk içeren dosya adlarını karakter çift tırnak işareti içine alınmalıdır. Kısmi bir yolu, geçerli bir sürücüsü olmasını CL varsayar sürücü adı atlar. Bir yol belirtmezseniz, CL dosya geçerli dizinde olduğu varsayılır.

Dosya adı uzantısı dosyaları nasıl işleneceğini belirler. Uzantı .c, .cxx veya .cpp sahip, C ve C++ dosyaları derlenir. .Obj dosyaları, kitaplık (.lib) ve modül-tanımlama (.def) dosyaları gibi diğer dosyalar için bağlayıcı işlenen olmadan geçirilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)