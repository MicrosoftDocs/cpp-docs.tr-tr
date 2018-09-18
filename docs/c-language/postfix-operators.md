---
title: Sonek işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d8d3a762cb3eed3b0182185561c33b073b571b1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036065"
---
# <a name="postfix-operators"></a>Sonek İşleçleri

Sonek işleçleri ifade değerlendirmesinde (tightest bağlama) en yüksek önceliğe sahip.

## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Birincil ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi***[***ifade***]** <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi***(***bağımsız değişken ifade listesi*<sub>iyileştirilmiş</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi***.**  *tanımlayıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi***->***tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

Bu öncelik düzeyi işleci bir dizi indisi, işlev çağrıları, yapı ve birleşim üyeleri ve sonek artırma ve azaltma işleçleri.

## <a name="see-also"></a>Ayrıca Bkz.

[C İşleçleri](../c-language/c-operators.md)