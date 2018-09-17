---
title: LINK ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88ac63ace95ac0b9874dc3376210f3f5b4af320
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716664"
---
# <a name="link-environment-variables"></a>LINK Ortam Değişkenleri

Bağlantı aracını aşağıdaki ortam değişkenleri kullanır:

- BAĞLANTI ve \_bağlantı\_, tanımlı değilse. BAĞLANTI araç seçenekleri ve bağlantı ortam değişkeninde tanımlanan değişkenleri ekler ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_bağlantı\_ işlemeden önce komut satırı bağımsız değişkenleri ortam değişkeni.

- LIB, tanımlı değilse. BAĞLANTI araçları, bir nesne, kitaplık veya komut satırında ya da belirtilen başka bir dosya ararken LIB yolunu kullanır [/BASE](../../build/reference/base-base-address.md) seçeneği. Ayrıca bir nesnedeki adlı bir .pdb dosyası bulmak için LIB yolunu kullanır. LIB değişkeni, noktalı virgülle ayrılmış bir veya daha fazla yol özellikleri içerebilir. Bir yol, Visual C++ yüklemenizin \lib alt dizinine işaret etmelidir.

- YOL, aracın CVTRES çalıştırmaya gerek duymadığı ve bağlantının kendisi ile aynı dizinde dosya bulunamıyor. (Bağlantı CVTRES bir .res dosyası bağlamanız gerekir.) YOL, Visual C++ yüklemenizin \bin alt dizinine işaret etmelidir.

- TMP, OMF veya .res dosyaları bağlanırken bir dizin belirtmek için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[Komut satırında C/C++ kodu derleme](../../build/building-on-the-command-line.md)<br/>
[Komut Satırı Derlemeleri için Yolu ve Ortam Değişkenlerini Ayarlama](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
