---
title: Bağlayıcı Seçeneklerini Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
ms.openlocfilehash: 5b885ad5c86bc59029fc6a3a60ccee385703ab2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508946"
---
# <a name="setting-linker-options"></a>Bağlayıcı Seçeneklerini Ayarlama

Bağlayıcı seçenekleri içinde veya dışında geliştirme ortamı ayarlayabilirsiniz. Her bağlayıcı seçeneği için konu, geliştirme ortamında nasıl ayarlanabilir açıklar. Bkz: [bağlayıcı seçenekleri](../../build/reference/linker-options.md) tam listesi için.

Geliştirme ortamının dışında bağlantı çalıştırdığınızda, bir veya daha fazla şekilde giriş belirtebilirsiniz:

- Üzerinde [komut satırı](../../build/reference/linker-command-line-syntax.md)

- Kullanarak [komut dosyaları](../../build/reference/link-command-files.md)

- İçinde [ortam değişkenleri](../../build/reference/link-environment-variables.md)

İlk işlem seçeneklerinin bağlantı seçenekleri komut satırında belirtilen bunlar sırada ve komut dosyaları tarafından izlenen bağlantı ortam değişkeninde belirtilen. Bir seçenek farklı bağımsız değişkenler yinelenirse işlediği son olaydan önceliklidir.

Seçenekler, tüm derleme için geçerlidir; belirli bir giriş dosyaları için seçenekleri uygulanabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)