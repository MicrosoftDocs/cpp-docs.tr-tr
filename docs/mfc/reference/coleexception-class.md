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
ms.openlocfilehash: 731ec7b359995fc8ecbfdeae89595442d8186eeb
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851398"
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
  
 SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK.  
  
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
  
 SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CALCDRIV](../../visual-cpp-samples.md)   
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



