---
title: . Bağlayıcı girişi olarak exp dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4badc93f38d5ce76dcc294ad4ae216c8e3f6454c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724015"
---
# <a name="exp-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Exp Dosyaları

Dışarı aktarma (.exp) dosyaları dışarı aktarılan işlevleri ve verileri öğeler hakkındaki bilgileri içerir. LIB içeri aktarma kitaplığı oluşturduğunda, ayrıca bir .exp dosyası oluşturur. Hem verir ve doğrudan veya dolaylı olarak başka bir programdan alır bir program bağladığınızda .exp dosyası kullanın. .Exp dosyasının ile bağlarsanız, LIB zaten bir oluşturduğunuzu varsayar çünkü bağlantı bir içeri aktarma kitaplığını üretmez. .Exp dosyaları ve içeri aktarma kitaplıkları hakkında daha fazla ayrıntı için bkz: [içeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma](../../build/reference/working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>Ayrıca Bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)