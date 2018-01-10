---
title: "CRichEditDoc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
dev_langs: C++
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c427dc034a37bf3b0686b0fd95e62c3b718fbaea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cricheditdoc-class"></a>CRichEditDoc sınıfı
İle [CRichEditView](../../mfc/reference/cricheditview-class.md) ve [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), zengin düzenleme denetimine MFC'nin belge görünüm mimarisi bağlamında işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Belgenin temizlenmesini için çağrılır.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Akış giriş ve çıkış biçimlendirme bilgileri içerip içermeyeceğini gösterir.|  
|[CRichEditDoc::GetView](#getview)|Asssociated alır [CRichEditView](../../mfc/reference/cricheditview-class.md) nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|Akış g/ç biçimlendirme içerip içermeyeceğini gösterir.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Zengin düzenleme denetimi" kullanıcı girin ve metin düzenleme bir penceredir. Metin karakter ve paragraf biçimlendirmesini atanabilir ve katıştırılmış OLE nesnelerine içerebilir. Zengin düzenleme denetimlerinde metin biçimlendirme için bir programlama arabirimi sağlar. Ancak, bir uygulamanın tüm biçimlendirme işlemlerini kullanıcı için kullanılabilir hale getirmek için gerekli olan kullanıcı arabirimi bileşenlerini uygulamalıdır.  
  
 `CRichEditView`metin ve biçimlendirme karakteristiğini metin, tutar. `CRichEditDoc`görünümde olan istemci öğeleri listesini tutar. `CRichEditCntrItem`OLE istemci öğeleri kapsayıcı tarafı erişim sağlar.  
  
 Bu Windows yaygın bir denetim (ve bu nedenle [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) ve ilgili sınıflar) yalnızca Windows 95/98 ve Windows NT sürümler 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Zengin düzenleme belge bir MFC uygulamasında kullanma örneği için bkz: [WORDPAD](../../visual-cpp-samples.md) örnek uygulama.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxrich.h  
  
##  <a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Oluşturmak için bu işlevi çağırmak bir `CRichEditCntrItem` nesne ve bu belgeye ekleyin.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Parametreler  
 *preo*  
 İşaretçi bir [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) OLE öğeyi tanımlayan yapısı. Yeni `CRichEditCntrItem` nesnesi, bu OLE öğenin etrafında yapılandırılmıştır. Varsa *preo* olan **NULL**, yeni istemci öğesi boş.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir işaretçi [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) bu belgeye eklenen bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, tüm OLE başlatma işlemini gerçekleştirir.  
  
 Daha fazla bilgi için bkz: [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) Windows SDK'sındaki yapısı.  
  
##  <a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Zengin düzenleme içeriğini akış için metin biçimi belirlemek için bu işlevini çağırın.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki bayraklardan biri:  
  
- `SF_TEXT`Zengin düzenleme denetimine biçimlendirme bilgisi içermez gösterir.  
  
- `SF_RTF`Zengin düzenleme denetimine biçimlendirme bilgilerini korur gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri dayanır [m_bRTF](#m_brtf) veri üyesi. Bu işlev, döndürür `SF_RTF` varsa `m_bRTF` olan **TRUE**; Aksi halde, `SF_TEXT`.  
  
##  <a name="getview"></a>CRichEditDoc::GetView  
 Erişmek için bu işlevi çağırmak [CRichEditView](../../mfc/reference/cricheditview-class.md) bununla ilişkili nesne `CRichEditDoc` nesne.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi `CRichEditView` belgeyle ilişkili nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin ve biçimlendirme bilgileri içinde bulunan `CRichEditView` nesnesi. `CRichEditDoc` Nesne seri hale getirme OLE öğeleri tutar. Olmamalıdır tek `CRichEditView` her `CRichEditDoc`.  
  
##  <a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 Zaman **TRUE**, belirten [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) ve [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) paragraf ve karakter biçimlendirme özelliklerini depolamanız gerekir.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek WORDPAD](../../visual-cpp-samples.md)   
 [COleServerDoc sınıfı](../../mfc/reference/coleserverdoc-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRichEditView sınıfı](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem sınıfı](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument sınıfı](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl Sınıfı](../../mfc/reference/cricheditctrl-class.md)
