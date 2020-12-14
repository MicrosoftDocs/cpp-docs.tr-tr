---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK2039'
title: Bağlayıcı Araçları Hatası LNK2039
ms.date: 11/04/2016
f1_keywords:
- LNK2039
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
ms.openlocfilehash: 34bddbd456e8e588ff6f7818d8db1d3522ccd06a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275639"
---
# <a name="linker-tools-error-lnk2039"></a>Bağlayıcı Araçları Hatası LNK2039

\<type>başka bir. obj içinde tanımlanmış olan ' ' başvuru sınıfı içeri aktarılıyor; içeri aktarılmalı ya da tanımlanmalıdır, ikisi birden değil

' <`type`> ' başvuru sınıfı belirtilen. obj dosyasında içeri aktarılır, ancak başka bir. obj dosyasında da tanımlanmıştır. Bu durum, çalışma zamanı hatasına veya diğer beklenmeyen davranışlara neden olabilir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. ' ' Nin `type` diğer. obj dosyasında tanımlanıp tanımlanmayacağını denetleyin ve. winmd dosyasından içeri aktarılmalıdır.

1. Tanımı ya da içeri aktarmayı kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları hataları ve uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)<br/>
[Bağlayıcı Araçları hatası LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
