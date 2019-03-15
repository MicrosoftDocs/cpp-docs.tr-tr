---
title: Bağlayıcı Girişi olarak .Ilk Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 252c1cd6e17346954fce7ebf16134246da76ba57
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808475"
---
# <a name="ilk-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Ilk Dosyaları

Artımlı bağlantılandırma, bağlantı ilk artımlı bağlantı sırasında oluşturulan .ilk durum dosyası güncelleştirir. Bu dosya .exe veya .dll dosyası olarak aynı temel ada sahiptir ve uzantı .ilk vardır. Sonraki artımlı bağlantılar sırasında bağlantı .ilk dosyası güncelleştirir. .İlk dosyası eksikse, bağlantı tam bağlantı gerçekleştirir ve yeni bir .ilk dosyası oluşturur. .İlk dosyası kullanılamıyor, artımlı olmayan bir bağlantı bağlantı gerçekleştirir. Artımlı bağlama hakkında daha fazla ayrıntı için bkz [artımlı bağlantı (/ INCREMENTAL)](incremental-link-incrementally.md) seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](link-input-files.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
