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
ms.openlocfilehash: b20f88e69c6e0d1774f1cd81b3ee833c4f0ff696
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811777"
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi

CL dosya FAT, HPFS veya NTFS adlandırma kurallarına uygun adlarla kabul eder. Herhangi bir dosya adının, tam veya kısmi bir yol dahil edebilirsiniz. Tam yol, bir sürücü adı ve bir veya daha fazla dizin adlarını içerir. CL kabul dosya adları ters eğik çizgi ile ayrılmış (\\) veya İleri eğik çizgi (/). Boşluk içeren dosya adlarını karakter çift tırnak işareti içine alınmalıdır. Kısmi bir yolu, geçerli bir sürücüsü olmasını CL varsayar sürücü adı atlar. Bir yol belirtmezseniz, CL dosya geçerli dizinde olduğu varsayılır.

Dosya adı uzantısı dosyaları nasıl işleneceğini belirler. Uzantı .c, .cxx veya .cpp sahip, C ve C++ dosyaları derlenir. .Obj dosyaları, kitaplık (.lib) ve modül-tanımlama (.def) dosyaları gibi diğer dosyalar için bağlayıcı işlenen olmadan geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
