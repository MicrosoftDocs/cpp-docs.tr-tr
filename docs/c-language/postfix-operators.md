---
description: 'Daha fazla bilgi edinin: sonek Işleçleri'
title: Sonek İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
ms.openlocfilehash: be8e7354d512174a4ab11ffcdcb82f9418baa894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195872"
---
# <a name="postfix-operators"></a>Sonek İşleçleri

Sonek işleçleri, ifade değerlendirmesinde en yüksek önceliğe (daha sıkı test bağlaması) sahiptir.

## <a name="syntax"></a>Syntax

*sonek ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*birincil ifade*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **[**  *ifade*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek-ifade*  **(**  *bağımsız değişken-ifade-List*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **.**  *Tanımlayıcısını*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi* **->** *tanımlayıcı*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*sonek ifadesi*  **--**

Bu öncelik düzeyindeki işleçler dizi alt simgeler, işlev çağrıları, yapı ve birleşim üyeleri ve Sonek artışı ve azaltma işleçleri olur.

## <a name="see-also"></a>Ayrıca bkz.

[C Işleçleri](../c-language/c-operators.md)
