---
description: 'Daha fazla bilgi edinin: CCreateContext yapısı'
title: CCreateContext yapısı
ms.date: 11/04/2016
f1_keywords:
- CCreateContext
helpviewer_keywords:
- CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
ms.openlocfilehash: b0d8c3a38d4d6ce9ee6130092ea6b27a50ed15e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220467"
---
# <a name="ccreatecontext-structure"></a>CCreateContext yapısı

Framework, `CCreateContext` bir belgeyle ilişkili çerçeve pencerelerini ve görünümlerini oluşturduğunda yapıyı kullanır.

## <a name="syntax"></a>Syntax

```
struct CCreateContext
```

## <a name="remarks"></a>Açıklamalar

`CCreateContext` bir yapıdır ve temel bir sınıfa sahip değildir.

Bir pencere oluşturduğunuzda, bu yapıdaki değerler bir belgenin bileşenlerini verilerinin görünümüne bağlamak için kullanılan bilgileri sağlar. Yalnızca `CCreateContext` oluşturma işleminin parçalarını geçersiz kılıyorsa kullanmanız gerekir.

Bir `CCreateContext` Yapı, belge, çerçeve penceresi, görünüm ve belge şablonu için işaretçiler içerir. Ayrıca `CRuntimeClass` , oluşturulacak görünüm türünü tanımlayan öğesine bir işaretçi içerir. Çalışma zamanı sınıfı bilgileri ve geçerli belge işaretçisi, dinamik olarak yeni bir görünüm oluşturmak için kullanılır. Aşağıdaki tabloda, her üyenin nasıl ve ne zaman `CCreateContext` kullanıldığı gösterilmektedir:

|Üye|Tür|Ne için|
|------------|----------|--------------------|
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass` oluşturulacak yeni görünümün.|
|`m_pCurrentDoc`|`CDocument*`|Yeni görünümle ilişkilendirilecek varolan belge.|
|`m_pNewDocTemplate`|`CDocTemplate*`|Yeni bir MDI çerçevesi penceresi oluşturma ile ilişkili belge şablonu.|
|`m_pLastView`|`CView*`|Ayırıcı pencere görünümlerinin oluşturulmasında veya belge üzerinde ikinci bir görünümün oluşturulmasına göre, ek görünümlerin modellendiği orijinal görünüm.|
|`m_pCurrentFrame`|`CFrameWnd*`|Belge üzerinde ikinci bir çerçeve penceresi oluştururken olduğu gibi, ek çerçeve pencerelerinin modellendiği çerçeve penceresi.|

Belge şablonu bir belge ve ilişkili bileşenlerini oluşturduğunda, yapıda depolanan bilgileri doğrular `CCreateContext` . Örneğin, varolmayan bir belge için bir görünüm oluşturulmamalıdır.

> [!NOTE]
> İçindeki tüm işaretçiler `CCreateContext` isteğe bağlıdır ve `NULL` belirtilmemişse veya bilinmiyorsa olabilir.

`CCreateContext` , "Ayrıca bkz." altında listelenen üye işlevleri tarafından kullanılır. Geçersiz kılmayı planlıyorsanız, belirli bilgiler için bu işlevlerin açıklamalarını inceleyin.

Birkaç genel yönerge aşağıda verilmiştir:

- , Ve ' de olduğu gibi, pencere oluşturma için bir bağımsız değişken olarak geçirildiğinde, `CWnd::Create` `CFrameWnd::Create` `CFrameWnd::LoadFrame` Oluştur bağlamı yeni pencerenin ne bağlanması gerektiğini belirtir. Çoğu pencere için tüm yapı isteğe bağlıdır ve bir `NULL` işaretçi geçirilebilir.

- Geçersiz kılınabilir üye işlevleri için `CFrameWnd::OnCreateClient` `CCreateContext` bağımsız değişken isteğe bağlıdır.

- Görünüm oluşturma ' da yer alan üye işlevleri için, görünümü oluşturmak için yeterli bilgi sağlamanız gerekir. Örneğin, bir bölücü penceresindeki ilk görünüm için sınıf bilgilerini ve geçerli belgeyi sağlamanız gerekir.

Genel olarak, Framework varsayılan değerlerini kullanırsanız, yoksayabilirsiniz `CCreateContext` . Daha gelişmiş değişiklikler yapmaya çalışırsanız, Microsoft Foundation Class Kitaplığı kaynak kodu veya VIEWEX gibi örnek programlar sizi yönlendirecektir. Gerekli bir parametreyi unutursanız, bir çerçeve onaylama işlemi ne olduğunu söyleyecektir.

Hakkında daha fazla bilgi için `CCreateContext` bkz. MFC örnek [viewex](../../overview/visual-cpp-samples.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxext. h

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd:: Create](../../mfc/reference/cframewnd-class.md#create)<br/>
[CFrameWnd:: LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)<br/>
[CFrameWnd:: OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)<br/>
[CSplitterWnd:: Create](../../mfc/reference/csplitterwnd-class.md#create)<br/>
[CSplitterWnd:: CreateView](../../mfc/reference/csplitterwnd-class.md#createview)<br/>
[CWnd:: Create](../../mfc/reference/cwnd-class.md#create)
