---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: a74a5336e626f561f1fc61e866792ce193332d84
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75316544"
---
# <a name="assume"></a>ASSUME

Kayıt değerlerinin hata denetimini sunar. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> *Segregister*__varsay:__ *Name* ⟦ __,__ *segregister* __:__ *Name*... ⟧\
> *Dataregister* __:__ *Type* ⟦ __,__ *dataregister* __:__ *Type*... ⟧\
> *Kayıt*varsay __: hata__ ⟦ __,__ *kayıt* __: hata__... ⟧\
> **⟦** *Register* __:__ ⟧**nothıng** ⟦ __,__ *yazmaç* __: nothıng__... ⟧

## <a name="remarks"></a>Açıklamalar

Bir **varsay** etkin olduktan sonra, derleyici verilen yazmaçların değerlerine yapılan değişiklikleri izler. Kayıt kullanılırsa **hata** oluşturur. **Hiçbir şey** kaydetme hata denetimini siler. Tek bir ifadede farklı tür varsayımları birleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
