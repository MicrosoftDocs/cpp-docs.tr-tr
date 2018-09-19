---
title: _com_error::Error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d56fcf7faaee9d3b0e02964163aa62372a30a78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109306"
---
# <a name="comerrorerror"></a>_com_error::Error

**Microsoft'a özgü**

Oluşturucuya geçirilen HRESULT alır.

## <a name="syntax"></a>Sözdizimi

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

Ham HRESULT öğesi, oluşturucuya geçirilen.

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş HRESULT öğeyi alır bir `_com_error` nesne.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)