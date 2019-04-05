---
title: Bağlayıcı Araçları Hatası LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 57d0c101358f84816c8d0cf96eb5137833df0b48
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027580"
---
# <a name="linker-tools-error-lnk2039"></a>Bağlayıcı Araçları Hatası LNK2039

başvuru sınıfı içeri aktarma\<türü >' another.obj içinde tanımlandığından,, içeri aktarılan veya tanımlı, ancak ikisi birden değil olmalıdır

Başvuru sınıfı ' <`type`>' belirtilen .obj dosyasında alınır, ancak ayrıca başka bir .obj dosyasında tanımlı değil. Bu durum, çalışma zamanı hatası ya da diğer beklenmeyen davranışlara neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Denetleme olmadığını '`type`' diğer .obj dosyasında tanımlanmış olmalıdır ve bu .winmd dosyanın aktarılmalıdır olup olmadığını denetleyin.

1. Tanım veya içeri aktarma kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Bağlayıcı Araçları Hatası LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)