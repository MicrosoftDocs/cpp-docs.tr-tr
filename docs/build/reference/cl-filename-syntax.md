---
description: 'Daha fazla bilgi edinin: CL filename sözdizimi'
title: CL Dosya Adı Sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: c7a657b54f69e2cdc0a126c55bb4102589a84290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182449"
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi

CL, FAT, HPFS veya NTFS adlandırma kurallarını izleyen adlara sahip dosyaları kabul eder. Herhangi bir dosya adı tam veya kısmi yol içerebilir. Tam yol bir sürücü adı ve bir veya daha fazla dizin adı içerir. CL ters eğik çizgi ( \\ ) veya eğik çizgi (/) ile ayrılmış dosya adlarını kabul eder. Boşluk içeren dosya adları çift tırnak karakterleriyle çevrelenmelidir. Kısmi bir yol sürücü adını atlar ve bu, CL 'nin geçerli sürücü olduğunu varsayar. Bir yol belirtmezseniz, CL dosyanın geçerli dizinde olduğunu varsayar.

Dosya adı uzantısı dosyaların nasıl işlendiğini belirler. . C,. cxx veya. cpp uzantısına sahip C ve C++ dosyaları derlenir. . Obj dosyaları, kitaplıklar (. lib) ve modül tanım (. def) dosyaları da dahil olmak üzere diğer dosyalar, işlem yapılmadan bağlayıcıya geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
