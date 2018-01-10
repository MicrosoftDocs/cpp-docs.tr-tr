---
title: "CL dosya adı sözdizimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fc9ce614cb67bef1904e8dc464402f362b0cbde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cl-filename-syntax"></a>CL Dosya Adı Sözdizimi
CL FAT, HPFS veya NTFS adlandırma kurallarına uygun adlara sahip dosyaları kabul eder. Tüm dosya adı bir tam veya kısmi yol içerebilir. Bir tam yol, bir sürücü adı ve bir veya daha fazla dizin adlarını içerir. CL kabul dosya adları ayrılmış ya da ters eğik çizgi (\\) veya eğik (/). Boşluk içeren dosya adları çift tırnak karakteri ile alınmalıdır. Kısmi bir yolun geçerli sürücü olmasını CL varsayar sürücü adı atlar. Bir yol belirtmezseniz, CL dosya geçerli dizinde olduğunu varsayar.  
  
 Dosya adı uzantısı dosyaları nasıl işlendiğini belirler. Uzantı .c, .cxx veya .cpp varsa, C ve C++ dosyaları derlenir. Modül-tanımlama (.def) dosyaları, .obj dosyaları ve kitaplıkları (.lib) dahil, diğer dosyalar için bağlayıcı işlenen olmadan geçirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)