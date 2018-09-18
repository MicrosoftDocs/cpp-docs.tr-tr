---
title: Matematik hatası M6202 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6202
dev_langs:
- C++
helpviewer_keywords:
- M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 328336e61c299cf9b9816ddfce7212f1798eae37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058555"
---
# <a name="math-error-m6202"></a>Matematik Hatası M6202

'function': _sıng hata

Verilen işlevin bağımsız değişkeni, bu işlev için singularity değerindeydi. İşlevi, bağımsız değişkeni tanımlanmadı.

Bu hata çağırır `_matherr` işlevi işlev adı, bağımsız ve hata türü. Yeniden yazabilirsiniz `_matherr` belirli çalışma zamanı kayan nokta matematik hataları işleme özelleştirmek için işlevi.