---
title: Windows İletisi Makroları
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: a5a6d45c64d6123128ae362c1ef5643392439f41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329405"
---
# <a name="windows-messages-macros"></a>Windows İletisi Makroları

Bu makro pencere iletilerini iletin.

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|Bir pencere tarafından alınan bir iletiyi işlenmek üzere başka bir pencereye iletmek için kullanın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG

Bu makro, bir pencere tarafından alınan bir iletiyi işlenmek üzere başka bir pencereye iletilir.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse sıfır değil, değilse sıfır.

### <a name="remarks"></a>Açıklamalar

Bir pencere tarafından alınan bir iletiyi işlenmek üzere başka bir pencereye iletmek için WM_FORWARDMSG kullanın. LPARAM ve WPARAM parametreleri aşağıdaki gibi kullanılır:

|Parametre|Kullanım|
|---------------|-----------|
|Wparam|Kullanıcı tarafından tanımlanan veriler|
|Lparam|İleti hakkında `MSG` bilgi içeren bir yapıya işaretçi|

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `m_hWndOther` bu iletiyi alan diğer pencereyi temsil eder.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
