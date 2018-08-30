---
title: COleException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a472de31695ab6038cab9ba0158580f3d305194
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212494"
---
# <a name="coleexception-class"></a>COleException sınıfı
Bir OLE işlemiyle ilgili bir özel durum koşulunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleException::Process](#process)|OLE dönüş koda yakalanan bir özel durumu çevirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Özel durumun nedenini gösteren durum kodu içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleException` Sınıfı özel durumun nedenini gösteren durum kodunu içeren bir genel veri üyesi içerir.  
  
 Genel olarak, değil oluşturacağınız bir `COleException` doğrudan; bunun yerine, çağırmalıdır nesne [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Özel durumları hakkında daha fazla bilgi için bkz: makaleleri [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="m_sc"></a>  COleException::m_sc  
 Bu veri üyesi, özel durumun nedenini gösteren OLE durum kodu içerir.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değişkenin değeri ayarlanır [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>  COleException::Process  
 Çağrı **işlem** yakalanan bir özel durumu bir OLE durumu koda çevirmek için üye işlevi.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Parametreler  
 *pAnyException*  
 Özel durum yakalandı işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE durum kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu işlev, **statik**.  
  
 SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CALCDRIV](../../visual-cpp-samples.md)   
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



