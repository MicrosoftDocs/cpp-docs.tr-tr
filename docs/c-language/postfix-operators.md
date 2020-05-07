---
title: Sonek İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
ms.openlocfilehash: a86ede25feeaee3a9fb1c6b146cf9667b85c0c2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232253"
---
# <a name="postfix-operators"></a>Sonek İşleçleri

Sonek işleçleri, ifade değerlendirmesinde en yüksek önceliğe (daha sıkı test bağlaması) sahiptir.

## <a name="syntax"></a>Sözdizimi

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birincil ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **[**  *ifade*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **(**  *bağımsız değişken-ifade-List*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **.**  *Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **->**  *tanımlayıcısı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

Bu öncelik düzeyindeki işleçler dizi alt simgeler, işlev çağrıları, yapı ve birleşim üyeleri ve Sonek artışı ve azaltma işleçleri olur.

## <a name="see-also"></a>Ayrıca bkz.

[C Işleçleri](../c-language/c-operators.md)
