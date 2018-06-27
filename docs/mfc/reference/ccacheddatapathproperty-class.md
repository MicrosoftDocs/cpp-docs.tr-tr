---
title: CCachedDataPathProperty sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b264b2366ce4fb7234d5906222fb4f8aa750212
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951422"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty sınıfı
Implements bir OLE zaman uyumsuz olarak aktarılır ve bellek dosyasında önbelleğe özelliğini denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Oluşturan bir `CCachedDataPathProperty` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` verileri önbelleğe nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bellek dosyası RAM yerine disk üzerinde depolanır ve hızlı geçici aktarımları için yararlıdır.  
  
 İle birlikte `CAysncMonikerFile` ve `CDataPathProperty`, `CCachedDataPathProperty` OLE denetimlerinde zaman uyumsuz adlar kullanmak için işlevsellik sağlar. İle `CCachedDataPathProperty` nesneleri, verileri zaman uyumsuz olarak bir URL veya dosya kaynaktan aktarmak ve bellek dosyası depolamak için `m_Cache` genel değişkeni. Tüm verileri bellek dosyasında depolanan ve geçersiz kılmak için gerek yoktur [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) bildirimleri için izleme ve yanıt istemiyorsanız. Örneğin, büyük bir aktarıyorsanız. GIF dosyası ve daha fazla veri geldi ve kendisini yeniden denetiminizi bildirmek isterseniz geçersiz kılma `OnDataAvailable` bildirim yapma.  
  
 Sınıf `CCachedDataPathProperty` türetildiği `CDataPathProperty`.  
  
 Zaman uyumsuz adlar ve ActiveX denetimlerini Internet uygulamalarında kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
- [Internet ilk adımlar: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internet ilk adımlar: Zaman uyumsuz adlar](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty  
 Oluşturan bir `CCachedDataPathProperty` nesnesi.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pControl*  
 Bu ile ilişkilendirilmesi ActiveX denetim nesnesi için bir işaretçi `CCachedDataPathProperty` nesnesi.  
  
 *lpszPath*  
 Mutlak veya göreli olabilir, yolun özelliği gerçek mutlak konumu başvuran zaman uyumsuz bir ad oluşturmak için kullanılır. `CCachedDataPathProperty` URL'ler, değil dosya adlarını kullanır. İsterseniz bir `CCachedDataPathProperty` nesne için bir dosya, yola file:// önüne ekleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 `COleControl` Tarafından için nesne işaret *pControl* tarafından kullanılan [açık](../../mfc/reference/cdatapathproperty-class.md#open) ve türetilmiş sınıfları tarafından alınır. Varsa *pControl* olan **NULL**, ile kullanılan denetimi `Open` ile ayarlamalıdır [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Varsa *lpszPath* olan **NULL**, yolundaki geçirebilirsiniz `Open` veya ile ayarlayın [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache  
 İçine verileri önbelleğe bellek dosyası sınıf adını içerir.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bellek dosyası RAM yerine disk üzerinde depolanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataPathProperty sınıfı](../../mfc/reference/cdatapathproperty-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)
