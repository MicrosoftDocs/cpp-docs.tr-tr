---
title: Windows iletisi makroları
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: 3ab102ec486af0c7119e8ed28da4898c8beeb293
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582526"
---
# <a name="windows-messages-macros"></a>Windows iletisi makroları

Bu makro, pencere iletilerini iletir.

|||
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|İşleme için başka bir pencere için bir pencere tarafından alınan bir iletiyi iletme için kullanın.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG

Bu makro, işleme için başka bir pencere için bir pencere tarafından alınan ileti iletir.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan bir ileti işlediğinde yoksa sıfır.

### <a name="remarks"></a>Açıklamalar

İşleme için başka bir pencere için bir pencere tarafından alınan bir iletiyi iletmesini WM_FORWARDMSG kullanın. LPARAM ve WPARAM Parametreler şu şekilde kullanılır:

|Parametre|Kullanım|
|---------------|-----------|
|WPARAM|Kullanıcı tarafından tanımlanan verileri|
|LPARAM|Bir işaretçi bir `MSG` bir ileti hakkında bilgi içeren yapısı|

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `m_hWndOther` bu iletiyi alır bir pencereyi temsil eder.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
