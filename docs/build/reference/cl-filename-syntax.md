---
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
ms.openlocfilehash: 1135e5c682b79fec5de808b61c93d370f05a3aa9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440231"
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi

CL, FAT, HPFS veya NTFS adlandırma kurallarını izleyen adlara sahip dosyaları kabul eder. Herhangi bir dosya adı tam veya kısmi yol içerebilir. Tam yol bir sürücü adı ve bir veya daha fazla dizin adı içerir. CL ters eğik çizgileri (\\) veya eğik çizgi (/) ile ayrılmış dosya adlarını kabul eder. Boşluk içeren dosya adları çift tırnak karakterleriyle çevrelenmelidir. Kısmi bir yol sürücü adını atlar ve bu, CL 'nin geçerli sürücü olduğunu varsayar. Bir yol belirtmezseniz, CL dosyanın geçerli dizinde olduğunu varsayar.

Dosya adı uzantısı dosyaların nasıl işlendiğini belirler. C ve C++ . c,. cxx veya. cpp uzantısına sahip dosyalar derlenir. . Obj dosyaları, kitaplıklar (. lib) ve modül tanım (. def) dosyaları da dahil olmak üzere diğer dosyalar, işlem yapılmadan bağlayıcıya geçirilir.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
