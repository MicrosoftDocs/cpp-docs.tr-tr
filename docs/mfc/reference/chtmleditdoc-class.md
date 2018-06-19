---
title: CHtmlEditDoc sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de452365a02b69798c62e2eecfd8051afcf08bb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366977"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc sınıfı
İle [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), MFC belge görünüm mimarisi bağlamında WebBrowser düzenleme platform işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Oluşturan bir `CHtmlEditDoc` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|Alır `CHtmlEditView` nesne bu belgeye eklendi.|  
|[CHtmlEditDoc::IsModified](#ismodified)|İlişkili görünümün WebBrowser denetimi kullanıcı tarafından değiştirilmiş bir belgenin içerip içermediğini döndürür.|  
|[CHtmlEditDoc::OpenURL](#openurl)|Bir URL açılır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc  
 Oluşturan bir **CHtmlEditDoc** nesnesi.  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>  CHtmlEditDoc::GetView  
 Alır [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) nesne bu belgeye eklendi.  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi belgenin döndüren **CHtmlEditView** nesnesi.  
  
##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified  
 İlişkili görünümün WebBrowser denetimi kullanıcı tarafından değiştirilmiş bir belgenin içerip içermediğini döndürür.  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL  
 Bir URL açılır.  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszURL`  
 Açmak için URL.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HTMLEdit örnek](../../visual-cpp-samples.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

