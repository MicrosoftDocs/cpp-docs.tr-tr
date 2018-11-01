---
title: CCreateContext yapısı
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: dd5659e7f91e3a2a1d653b61f12323ed1ae5a9b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438967"
---
# <a name="ccreatecontext-structure"></a>CCreateContext yapısı

Framework kullanan `CCreateContext` çerçeve pencereleri ve belge ile ilişkili olan görünümleri oluşturduğunda, yapı.

## <a name="syntax"></a>Sözdizimi

```
struct CCreateContext
```

## <a name="remarks"></a>Açıklamalar

`CCreateContext` bir yapı olduğunu ve bir temel sınıfa sahip değil.

Bir pencere oluşturduğunuzda, bu yapı değerleri belgenin bileşenleri kendi veri görünümüne bağlanmak için kullanılan bilgileri sağlayın. Yalnızca kullanmak zorunda `CCreateContext` oluşturma işlemini bölümlerini kılıyorsa.

A `CCreateContext` yapısı, belge, çerçeve penceresi, Görünüm ve belge şablonunu işaretçileri içerir. Ayrıca bir işaretçi içeren bir `CRuntimeClass` oluşturmak için görünüm türünü tanımlar. Çalışma süresi sınıf bilgilerine ve geçerli belge işaretçisi, dinamik olarak yeni bir görünüm oluşturmak için kullanılır. Aşağıdaki tabloda, nasıl ve ne zaman önerir her `CCreateContext` üyesi kullanılan:

|Üye|Tür|Ne işe yaradığını|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` Oluşturulacak yeni görünümü.|
|`m_pCurrentDoc`|`CDocument*`|Yeni Görünüm ile ilişkilendirilecek varolan belge.|
|`m_pNewDocTemplate`|`CDocTemplate*`|Yeni bir MDI çerçeve penceresi oluşturma ile ilişkili belge şablonu.|
|`m_pLastView`|`CView*`|Orijinal görünümde üzerinde ek görünümler, bölümlendirici pencere görünümleri oluşturma ya da bir belge üzerinde ikinci bir görünüm oluşturulmasını olduğu gibi modellenir.|
|`m_pCurrentFrame`|`CFrameWnd*`|Çerçeve penceresi üzerinde ek çerçeve pencereleri, bir belge ikinci bir çerçeve penceresinde oluşturulmasını olduğu gibi modellenir.|

Bir belge şablonu, bir belge ve ilişkili bileşenlerinin oluşturduğunda, depolanan bilgileri doğrular. `CCreateContext` yapısı. Örneğin, bir görünüm için varolmayan bir belge oluşturulmalı değil.

> [!NOTE]
>  Tüm işaretçi `CCreateContext` isteğe bağlıdır ve olabilir `NULL` belirtilmemiş veya bilinmeyen.

`CCreateContext` altında listelenen üye işlevleri tarafından kullanılan "Ayrıca bkz." Bu işlevlerin açıklamaları bunları geçersiz kılmak planlama için belirli bilgiler danışın.

Bazı genel yönergeler şunlardır:

- Pencere oluşturma için bağımsız değişken olarak geçirilen zaman `CWnd::Create`, `CFrameWnd::Create`, ve `CFrameWnd::LoadFrame`, oluşturma bağlamı ne yeni pencere bağlanması gerektiğini belirtir. Yapının tamamını çoğu windows için isteğe bağlıdır ve `NULL` işaretçi geçirilebilir.

- Geçersiz kılınabilir üye işlevleri için gibi `CFrameWnd::OnCreateClient`, `CCreateContext` bağımsız değişken isteğe bağlıdır.

- Dahil olan üye işlevleri için Görünüm oluşturma, görünümü oluşturmak için yeterli bilgi sağlamalısınız. Örneğin, bir ayırıcı penceresi ilk görünümü için sınıf bilgilerini görüntüle ve geçerli belgede sağlamalısınız.

Framework Varsayılanları kullanırsanız, genel olarak, yoksayabilirsiniz `CCreateContext`. Daha gelişmiş değişiklikler, Microsoft Foundation Class Kitaplığı kaynak kodunu veya örnek programlardan VIEWEX gibi çalışırsanız size yol gösterir. Gerekli parametre unutursanız, framework onaylama, unuttum bildirir.

Daha fazla bilgi için `CCreateContext`, MFC örnek görmek [VIEWEX](../../visual-cpp-samples.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxext.h

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Create](../../mfc/reference/cwnd-class.md#create)

