---
title: "CCreateContext yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CCreateContext
dev_langs: C++
helpviewer_keywords: CCreateContext structure [MFC]
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 900664f43b132b118a8da0b855d5d5291fd79fee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccreatecontext-structure"></a>CCreateContext yapısı
Çerçeve kullanır `CCreateContext` belge ile ilişkili görünümler ve çerçeve pencereleri oluşturduğunda yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CCreateContext`bir yapıdır ve bir taban sınıfı yok.  
  
 Bir pencere oluşturduğunuzda, bu yapıyı değerleri kendi veri görünümüne bir belge bileşenlerinin bağlanmak için kullanılan bilgiler sağlar. Yalnızca kullanmak zorunda `CCreateContext` bölümleri oluşturma işleminin kılıyorsa.  
  
 A `CCreateContext` yapısı belge, çerçeve penceresi, Görünüm ve belge şablonu işaretçiler içerir. Bir işaretçi de içeren bir `CRuntimeClass` oluşturmak için görünüm türünü tanımlar. Çalışma zamanı sınıf bilgileri ve geçerli belge işaretçisi dinamik olarak yeni bir görünüm oluşturmak için kullanılır. Aşağıdaki tabloda nasıl ve ne zaman önerilse her `CCreateContext` üye kullanılan:  
  
|Üye|Tür|İçin nedir|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`Oluşturulacak yeni görünümü.|  
|`m_pCurrentDoc`|`CDocument*`|Yeni görünümü ile ilişkilendirilecek mevcut belge.|  
|`m_pNewDocTemplate`|`CDocTemplate*`|Belge şablonu yeni bir MDI çerçeve penceresi oluşturma ile ilişkilendirilmiş.|  
|`m_pLastView`|`CView*`|Üzerinde ek görünümler, bölümlendirici pencere görünümleri oluşturma veya bir belge üzerinde ikinci bir görünüm oluşturma gibi Modellenen özgün görüntüleyin.|  
|`m_pCurrentFrame`|`CFrameWnd*`|Üzerinde ek çerçeve pencereleri, bir belge üzerinde ikinci bir çerçeve penceresi oluşturma gibi Modellenen çerçeve penceresi.|  
  
 Belge şablonu bir belge ve ilişkili bileşenlerini oluşturduğunda, depolanan bilgileri doğruladığı `CCreateContext` yapısı. Örneğin, bir görünüm için varolmayan bir belge oluşturulamaz.  
  
> [!NOTE]
>  Tüm İşaretçiler `CCreateContext` isteğe bağlıdır ve olabilir `NULL` belirtilmemiş ya da bilinmiyor.  
  
 `CCreateContext`altında listelenen üye işlevleri tarafından kullanılan "Ayrıca bkz." Geçersiz kılmadığınız planlıyorsanız, bu işlevler açıklamalarını özel bilgiler için başvurun.  
  
 Birkaç genel kurallar şunlardır:  
  
-   Pencere oluşturulması için bağımsız değişken olarak olarak geçirildiğinde `CWnd::Create`, `CFrameWnd::Create`, ve `CFrameWnd::LoadFrame`, ne yeni pencere bağlanması gerektiği Oluştur bağlam belirtir. Çoğu windows için tüm yapısını isteğe bağlıdır ve bir `NULL` işaretçi geçirilebilir.  
  
-   Geçersiz kılınabilir üye işlevleri için gibi `CFrameWnd::OnCreateClient`, `CCreateContext` bağımsız değişken isteğe bağlıdır.  
  
-   Söz konusu üye işlevleri için Görünüm oluşturma, görünüm oluşturmak için yeterli bilgi sağlamanız gerekir. Örneğin, bir Bölümlendirici pencere ilk görünüm için sınıf bilgileri görüntüleyin ve geçerli belge sağlamalısınız.  
  
 Genel olarak, framework varsayılanları kullanın, yoksayabilirsiniz `CCreateContext`. Daha gelişmiş değişiklikler, Microsoft Foundation Class Kitaplığı kaynak kodu veya VIEWEX gibi örnek programlar çalışırsanız size yol gösterecektir. Gerekli parametre unutursanız, framework onaylama ne unuttunuz söyler.  
  
 Daha fazla bilgi için `CCreateContext`, MFC örnek bkz [VIEWEX](../../visual-cpp-samples.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [CWnd::Create](../../mfc/reference/cwnd-class.md#create)

