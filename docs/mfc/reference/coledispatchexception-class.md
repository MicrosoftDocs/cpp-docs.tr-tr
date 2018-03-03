---
title: "COleDispatchException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d90c59e4f85c871c113e51063ef1d50997bb508b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="coledispatchexception-class"></a>COleDispatchException sınıfı
OLE belirli özel durumları işler `IDispatch` OLE Otomasyon önemli bir parçası olan arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Hata için Yardım bağlamı.|  
|[COleDispatchException::m_strDescription](#m_strdescription)|Sözlü hata açıklaması.|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Yardım dosyası ile birlikte kullanılmak üzere `m_dwHelpContext`.|  
|[COleDispatchException::m_strSource](#m_strsource)|Özel durum oluşturdu uygulama.|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-belirli bir hata kodu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Türetilmiş bir özel durum sınıflar gibi `CException` temel sınıfı, `COleDispatchException` ile kullanılan **THROW**, `THROW_LAST`, **deneyin**, **CATCH**, `AND_CATCH`, ve `END_CATCH` makroları.  
  
 Genel olarak, çağırmalıdır [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) başlatıldıysa ve oluşturmak için bir `COleDispatchException` nesnesi.  
  
 Özel durumlar hakkında daha fazla bilgi için makalelerine bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext  
 Uygulamanızın Yardımı'nda Yardım bağlamı tanımlar (. HLP) dosyası.  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi tarafından ayarlanan [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) ne zaman bir özel durum oluşur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strdescription"></a>COleDispatchException::m_strDescription  
 "Disk dolu." gibi sözlü hata açıklamasını içerir  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi tarafından ayarlanan [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) ne zaman bir özel durum oluşur.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile  
 Bu dize uygulamanın Yardım dosyasının adı ile framework doldurur.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="m_strsource"></a>COleDispatchException::m_strSource  
 Bu dize özel durum oluşturdu uygulamanın adı ile framework doldurur.  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_wcode"></a>COleDispatchException::m_wCode  
 Uygulamanız için belirli bir hata kodunu içeriyor.  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi tarafından ayarlanan [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) ne zaman bir özel durum oluşur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CALCDRIV](../../visual-cpp-samples.md)   
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDispatchDriver sınıfı](../../mfc/reference/coledispatchdriver-class.md)   
 [COleException Sınıfı](../../mfc/reference/coleexception-class.md)
