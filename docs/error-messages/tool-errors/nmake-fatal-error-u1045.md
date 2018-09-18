---
title: NMAKE önemli hatası U1045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2b9be4f7440d9e79d603e917c1886aebe7c44af
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056891"
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE Önemli Hatası U1045

üretme başarısız oldu: ileti

Bir program veya komut belirli bir nedenle başarısız NMAKE tarafından çağrılır. NMAKE başka bir program çağırdığında — Örneğin, derleyici veya bağlayıcı — çağrı başarısız olabilir veya çağrılan bir program tarafından döndürülen bir hata. Bu ileti, hatayı bildirmek için kullanılır.

Bu sorunu gidermek için önce hatanın nedenini belirleyin. NMAKE tarafından bildirilen komutları kullanabilirsiniz [/N](../../build/nmake-options.md) ortam ayarları doğrulayın ve komut satırında NMAKE tarafından gerçekleştirilen eylemlerin yinelemek için seçeneği.