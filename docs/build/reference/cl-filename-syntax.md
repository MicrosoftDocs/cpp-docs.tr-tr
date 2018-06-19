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
ms.openlocfilehash: 121cd8971be65e15ad6445cb347baf478046bf3e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370468"
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi
CL FAT, HPFS veya NTFS adlandırma kurallarına uygun adlara sahip dosyaları kabul eder. Tüm dosya adı bir tam veya kısmi yol içerebilir. Bir tam yol, bir sürücü adı ve bir veya daha fazla dizin adlarını içerir. CL kabul dosya adları ayrılmış ya da ters eğik çizgi (\\) veya eğik (/). Boşluk içeren dosya adları çift tırnak karakteri ile alınmalıdır. Kısmi bir yolun geçerli sürücü olmasını CL varsayar sürücü adı atlar. Bir yol belirtmezseniz, CL dosya geçerli dizinde olduğunu varsayar.  
  
 Dosya adı uzantısı dosyaları nasıl işlendiğini belirler. Uzantı .c, .cxx veya .cpp varsa, C ve C++ dosyaları derlenir. Modül-tanımlama (.def) dosyaları, .obj dosyaları ve kitaplıkları (.lib) dahil, diğer dosyalar için bağlayıcı işlenen olmadan geçirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)