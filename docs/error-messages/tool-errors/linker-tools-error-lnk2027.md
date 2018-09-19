---
title: Bağlayıcı araçları hatası LNK2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 022e363af575e29e3085dcaec21257fa7e4ab5f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116855"
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027

Çözümlenmemiş modül başvurusu 'module'

Bağlayıcı için geçirilen dosya tipleri ile belirtilen bir modülde bağımlılığa sahip **assemblymodule** ya da doğrudan bağlayıcıya geçirildi.

LNK2027 çözümlemek için aşağıdakilerden birini yapın:

- Bağlayıcı için modül bağımlılığının dosya geçirmeyin.

- Modülüyle belirtin **assemblymodule**.

- Güvenli bir .netmodule modülü ise modülü bağlayıcıya doğrudan geçirin.

Daha fazla bilgi için [assemblymodule (derlemeye MSIL Modülü Ekle)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).