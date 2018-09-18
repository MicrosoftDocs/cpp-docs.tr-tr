---
title: _com_error::HRESULTToWCode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c39b638451aa8ea89191e323eae5f2c140563990
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082072"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft'a özgü**

16 bit için 32 bitlik HRESULT eşler `wCode`.

## <a name="syntax"></a>Sözdizimi

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Parametreler

*İK*<br/>
16 bit eşlenmesi 32 bitlik HRESULT `wCode`.

## <a name="return-value"></a>Dönüş Değeri

16-bit `wCode` 32 bitlik HRESULT eşlenmiş.

## <a name="remarks"></a>Açıklamalar

Bkz: [_com_error::WCode](../cpp/com-error-wcode.md) daha fazla bilgi için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)