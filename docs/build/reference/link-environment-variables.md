---
title: LINK Ortam Değişkenleri
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- variables, environment
- LINK tool [C++], environment variables
- LIB environment variable
- environment variables [C++], LINK
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
ms.openlocfilehash: 3a398787530794f5a08d6cd122e55c305e265062
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434417"
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
