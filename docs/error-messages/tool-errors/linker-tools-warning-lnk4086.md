---
title: Bağlayıcı araçları uyarısı LNK4086 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21a2ee7660f0ad78d04f7edb191929296c8d47a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079238"
---
# <a name="linker-tools-warning-lnk4086"></a>Bağlayıcı Araçları Uyarısı LNK4086

Giriş Noktası 'function', 'number' bayt bağımsız değişken ile __stdcall değildir; Görüntü çalışmayabilir

Bir DLL giriş noktası olmalıdır `__stdcall`. Ya da ile işlevi derleyin [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) belirtin veya seçeneği `__stdcall` veya işlev tanımlanırken WINAPI.