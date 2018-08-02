---
title: _variant_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 567a3387e79244443b784549d6223a14f78103ce
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464690"
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft'a özgü**  
  
 Bağlanan bir `VARIANT` içine nesne **_variant_t** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void Attach(VARIANT& varSrc);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *varSrc*  
 A `VARIANT` için eklenecek nesne **_variant_t** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Sahipliğini `VARIANT` , şifrelenmiş olarak. Bu üye işlevi herhangi kapsüllenmiş varolan yayımlar `VARIANT`, ardından sağlanan kopyalar `VARIANT`ve ayarlar, `VARTYPE` emin olmak için VT_EMPTY kaynaklarını tarafından yalnızca yayımlanabilecek **_variant_t** yıkıcı.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)