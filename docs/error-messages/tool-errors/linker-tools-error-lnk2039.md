---
title: Bağlayıcı Araçları Hatası LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 7712747deb865ec62fa007fcd95ad09630d00cea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194505"
---
# <a name="linker-tools-error-lnk2039"></a>Bağlayıcı Araçları Hatası LNK2039

başka bir. obj; içinde tanımlanan '\<Type > ' başvuru sınıfı içeri aktarılıyor İçeri aktarılmalı ya da tanımlanmalıdır, ancak her ikisi birden belirtilmemelidir

' <`type`> ' başvuru sınıfı belirtilen. obj dosyasında içeri aktarıldı, ancak aynı zamanda başka bir. obj dosyasında da tanımlanmıştır. Bu durum, çalışma zamanı hatasına veya diğer beklenmeyen davranışlara neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. '`type`' ın diğer. obj dosyasında tanımlanması gerekip gerekmediğini denetleyin ve. winmd dosyasından içeri aktarılmalı olup olmadığını denetleyin.

1. Tanımı ya da içeri aktarmayı kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Bağlayıcı Araçları Hatası LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
