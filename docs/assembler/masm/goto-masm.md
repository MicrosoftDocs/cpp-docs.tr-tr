---
title: GOTO (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0be678e2d39389cbc551c386c1890f799124b5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691250"
---
# <a name="goto-masm"></a>GOTO (MASM)

İşaretlenmiş satırın derleme aktarır **:**_macrolabel_.

## <a name="syntax"></a>Sözdizimi

> **GOTO** *macrolabel*

## <a name="remarks"></a>Açıklamalar

**GOTO** yalnızca içinde izin [MAKROSU](macro.md), [için](for-masm.md), [FORC](forc.md), [YİNELEYİN](repeat.md), ve [çalışırken](while-masm.md)engeller. *Macrolabel* hedef satırında yalnızca yönergesi olmalıdır ve önde gelen iki nokta ile gelmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>
