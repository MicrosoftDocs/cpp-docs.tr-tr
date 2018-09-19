---
title: Bağlayıcı araçları uyarısı LNK4099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50bdceaba2e72312febec4819b96df334b5398c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026018"
---
# <a name="linker-tools-warning-lnk4099"></a>Bağlayıcı Araçları Uyarısı LNK4099

PDB 'filename', 'nesne/Kitaplık' veya 'path';'konumunda bulunamadı Nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

Bağlayıcı, .pdb dosyasını bulamadı. Dosyayı içeren dizine kopyalayın `object/library`.

Nesne dosyası ile ilişkili .pdb dosyasının adını bulmak için:

1. Bir nesne dosyası kitaplığı ile ayıklamak [LIB](../../build/reference/lib-reference.md) **/ayıklayın:**`objectname`**.obj** `xyz` **.lib**.

1. İle .pdb dosyasının yolunu denetleyin **dumpbin /section:.debug$ T /rawdata** `objectname` **.obj**.

İle derleme [/z7](../../build/reference/z7-zi-zi-debug-information-format.md), pdb kaldırın veya kullanılabilir gerekmez [/DEBUG](../../build/reference/debug-generate-debug-info.md) bağlandığınız nesneler için .pdb dosyası yoksa bağlayıcı seçeneği.