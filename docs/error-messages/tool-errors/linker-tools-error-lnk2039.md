---
title: Bağlayıcı Araçları Hatası LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: fad8960424cd73240d547ef894b2ae5cdf358601
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498288"
---
# <a name="linker-tools-error-lnk2039"></a>Bağlayıcı Araçları Hatası LNK2039

başvuru sınıfı içeri aktarma\<türü >' another.obj içinde tanımlandığından,, içeri aktarılan veya tanımlı, ancak ikisi birden değil olmalıdır

Başvuru sınıfı ' <`type`>' belirtilen .obj dosyasında alınır, ancak ayrıca başka bir .obj dosyasında tanımlı değil. Bu durum, çalışma zamanı hatası ya da diğer beklenmeyen davranışlara neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Denetleme olmadığını '`type`' diğer .obj dosyasında tanımlanmış olmalıdır ve bu .winmd dosyanın aktarılmalıdır olup olmadığını denetleyin.

1. Tanım veya içeri aktarma kaldırın.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Bağlayıcı Araçları Hatası LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)