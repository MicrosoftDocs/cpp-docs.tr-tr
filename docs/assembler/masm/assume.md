---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 73ef8bcc33087a56747b80f94482fcd6c50e3bf6
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399262"
---
# <a name="assume-32-bit-masm"></a>VARSAY (32-bit Masz)

Kayıt değerlerinin hata denetimini sunar. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> *Segregister*__varsay:__ *Name* ⟦ __,__ *segregister* __:__ *Name*... ⟧\
> *Dataregister* __:__ *Type* ⟦ __,__ *dataregister* __:__ *Type*... ⟧\
> *Kayıt*varsay __: hata__ ⟦ __,__ *kayıt* __: hata__... ⟧\
> **⟦** *Register* __:__ ⟧**nothıng** ⟦ __,__ *yazmaç* __: nothıng__... ⟧

## <a name="remarks"></a>Açıklamalar

Bir **varsay** etkin olduktan sonra, derleyici verilen yazmaçların değerlerine yapılan değişiklikleri izler. Kayıt kullanılırsa **hata** oluşturur. **Hiçbir şey** kaydetme hata denetimini siler. Tek bir ifadede farklı tür varsayımları birleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)
