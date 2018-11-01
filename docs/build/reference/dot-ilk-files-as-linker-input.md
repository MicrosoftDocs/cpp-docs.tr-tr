---
title: Bağlayıcı Girişi olarak .Ilk Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 012ca9aaa50ac2f8bb9d95ef77df5bb7127c5b79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595981"
---
# <a name="ilk-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Ilk Dosyaları

Artımlı bağlantılandırma, bağlantı ilk artımlı bağlantı sırasında oluşturulan .ilk durum dosyası güncelleştirir. Bu dosya .exe veya .dll dosyası olarak aynı temel ada sahiptir ve uzantı .ilk vardır. Sonraki artımlı bağlantılar sırasında bağlantı .ilk dosyası güncelleştirir. .İlk dosyası eksikse, bağlantı tam bağlantı gerçekleştirir ve yeni bir .ilk dosyası oluşturur. .İlk dosyası kullanılamıyor, artımlı olmayan bir bağlantı bağlantı gerçekleştirir. Artımlı bağlama hakkında daha fazla ayrıntı için bkz [artımlı bağlantı (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)