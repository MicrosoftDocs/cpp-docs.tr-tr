---
title: Bağlayıcı araçları hatası LNK2039 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac4fdde90911427a1a193bfb6f3a950a7bdcf180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081799"
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