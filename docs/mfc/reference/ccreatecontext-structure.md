---
title: CCreateContext Yapısı
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: 29fc6210b9888b6a5ba5aaf15b66242c29c15dc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369376"
---
# <a name="ccreatecontext-structure"></a>CCreateContext Yapısı

Çerçeve, çerçeve `CCreateContext` pencerelerini ve belgeyle ilişkili görünümleri oluştururken yapıyı kullanır.

## <a name="syntax"></a>Sözdizimi

```
struct CCreateContext
```

## <a name="remarks"></a>Açıklamalar

`CCreateContext`bir yapıdır ve taban sınıfa sahip değildir.

Bir pencere oluşturduğunuzda, bu yapıdaki değerler, belgenin bileşenlerini verilerinin görünümüne bağlamak için kullanılan bilgileri sağlar. Yalnızca oluşturma işleminin bazı bölümlerini geçersiz kılıyorsanız kullanmanız `CCreateContext` gerekir.

Yapı, `CCreateContext` belge, çerçeve penceresi, görünüm ve belge şablonu işaretçileri içerir. Ayrıca, oluşturulacak görünüm `CRuntimeClass` türünü tanımlayan bir işaretçi de içerir. Çalışma zamanı sınıf bilgileri ve geçerli belge işaretçisi dinamik olarak yeni bir görünüm oluşturmak için kullanılır. Aşağıdaki tablo, her `CCreateContext` üyenin nasıl ve ne zaman kullanılabileceğini önerir:

|Üye|Tür|Ne için|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`oluşturmak için yeni bir görünüm.|
|`m_pCurrentDoc`|`CDocument*`|Varolan belge yeni görünümle ilişkilendirilecek.|
|`m_pNewDocTemplate`|`CDocTemplate*`|Yeni bir MDI çerçeve penceresi oluşturulmasıyla ilişkili belge şablonu.|
|`m_pLastView`|`CView*`|Bölücü pencere görünümlerinin oluşturulmasında veya belgede ikinci bir görünüm oluşturulmasında olduğu gibi, ek görünümlerin modellendiği özgün görünüm.|
|`m_pCurrentFrame`|`CFrameWnd*`|Belgede ikinci bir çerçeve penceresi oluşturulmasında olduğu gibi, ek çerçeve pencerelerinin modellendiği çerçeve penceresi.|

Belge şablonu bir belge ve ilişkili bileşenleri oluşturduğunda, `CCreateContext` yapıda depolanan bilgileri doğrular. Örneğin, var olmayan bir belge için bir görünüm oluşturulmamalıdır.

> [!NOTE]
> Tüm işaretçiler `CCreateContext` isteğe bağlıdır ve `NULL` belirtilmemiş veya bilinmiyorsa olabilir.

`CCreateContext`altında listelenen üye işlevler tarafından kullanılır "Ayrıca bakınız." Bunları geçersiz kılmayı planlıyorsanız, belirli bilgiler için bu işlevlerin açıklamalarına başvurun.

Aşağıda birkaç genel yönerge verilmiştir:

- Pencere oluşturma bağımsız değişkeni olarak `CWnd::Create`geçirildiğinde, ,, ve `CFrameWnd::Create` `CFrameWnd::LoadFrame`, oluşturma bağlamı yeni pencerenin neye bağlanması gerektiğini belirtir. Çoğu pencere için tüm yapı isteğe bağlıdır ve bir `NULL` işaretçi geçirilebilir.

- Geçersiz kılınabilir üye işlevler `CFrameWnd::OnCreateClient`için, örneğin, `CCreateContext` bağımsız değişken isteğe bağlıdır.

- Görünüm oluşturmada yer alan üye işlevler için, görünümü oluşturmak için yeterli bilgi sağlamanız gerekir. Örneğin, bir ayırıcı penceresindeki ilk görünüm için görünüm sınıfı bilgilerini ve geçerli belgeyi sağlamanız gerekir.

Genel olarak, çerçeve varsayılanlarını kullanırsanız, `CCreateContext`göz ardı edebilirsiniz. Daha gelişmiş değişiklikler yapmaya çalışırsanız, Microsoft Foundation Class Library kaynak kodu veya VIEWEX gibi örnek programlar size yol gösterecektir. Gerekli bir parametreyi unutursanız, bir çerçeve iddiası size neyi unuttuğunuz hakkında bir şey söyler.

Daha fazla `CCreateContext`bilgi için MFC örneği [VIEWEX'e](../../overview/visual-cpp-samples.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext.h

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd::Oluştur](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd::Oluştur](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd::Oluştur](../../mfc/reference/cwnd-class.md#create)
