---
title: "Platform::RecreateException yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Exception
dev_langs: C++
helpviewer_keywords: Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: e617d85c17db3c1e3cccb64786dfe7bfcfb9b1e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException yöntemi
Bu yöntem yalnızca dahili kullanım içindir ve kullanıcı kodu için tasarlanmamıştır. Bunun yerine Exception::CreateException yöntemini kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parametreler
`hr`

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Yeni bir Platform::Exception döndürür ^, belirtilen HRESULT göre.

