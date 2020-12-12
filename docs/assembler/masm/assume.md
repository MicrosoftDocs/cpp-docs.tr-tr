---
description: 'Hakkında daha fazla bilgi edinin: varsay'
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: b597e50dafe07950d87cb04cf5e697b63c55611c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121751"
---
# <a name="assume"></a>ASSUME

Kayıt değerlerinin hata denetimini sunar. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Syntax

> *Segregister*__varsay:__*Name* ⟦__,__ *segregister*__:__*Name*... ⟧\  
> *Dataregister*__:__*Type* ⟦__,__ *dataregister*__:__*Type*... ⟧\  
> *Kayıt* varsay __: hata__ ⟦__,__ *kayıt*__: hata__... ⟧\  
> **⟦** *Register*__:__⟧**nothıng** ⟦__,__ *yazmaç*__: nothıng__... ⟧

## <a name="remarks"></a>Açıklamalar

Bir **varsay** etkin olduktan sonra, derleyici verilen yazmaçların değerlerine yapılan değişiklikleri izler. Kayıt kullanılırsa **hata** oluşturur. **Hiçbir şey** kaydetme hata denetimini siler. Tek bir ifadede farklı tür varsayımları birleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
