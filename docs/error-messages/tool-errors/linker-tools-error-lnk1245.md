---
title: Bağlayıcı araçları hatası LNK1245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef7bace5cec937399d7a2ed440e21b9b751f4141
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041798"
---
# <a name="linker-tools-error-lnk1245"></a>Bağlayıcı Araçları Hatası LNK1245

Geçersiz 'alt sistem belirtilmedi;' alt sistemi / SUBSYSTEM WINDOWS, WINDOWSCE veya KONSOL olmalıdır

[/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) nesne derlemek için kullanılan ve aşağıdaki koşullar doğru:

- Özel giriş noktası tanımlanmış ([/Entry](../../build/reference/entry-entry-point-symbol.md)), yani bir subsystem bağlayıcı çıkarılamadı.

- Bir değer geçildi [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) bağlayıcı seçeneği, / CLR nesneler için geçerli değil.

Her iki durum için çözüm/Subsystem bağlayıcı seçeneği için geçerli bir değer belirtmek içindir.