---
title: Atexit kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d5164394853d2ac4f18efc94863b8fc3fa5ba78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053134"
---
# <a name="using-atexit"></a>atexit Kullanma

İle [atexit](../c-runtime-library/reference/atexit.md) işlevi, program sonlanması öncesinde çalışan bir çıkış işleme işlevi belirtebilirsiniz. Çağrıdan önce başlatılan hiçbir genel statik nesneler **atexit** çıkış işleme işlevinin bir yürütme önce yok edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Ek Sonlandırma Konuları](../cpp/additional-termination-considerations.md)