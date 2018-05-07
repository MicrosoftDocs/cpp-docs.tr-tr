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
ms.openlocfilehash: 46f554e375e8c0185e8c2b75c81eeae5ee615c51
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coleexception-class"></a>COleException sınıfı
Bir OLE işlemle ilişkili bir özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleException::Process](#process)|Yakalanan bir özel durum OLE dönüş koda çevirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Özel durumun nedeni gösteren durum kodunu içerir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleException` Sınıfı, özel durumun nedeni gösteren durum kodu tutan bir genel veri üyesi içerir.  
  
 Genel olarak, size oluşturma bir `COleException` çağrı doğrudan; bunun yerine, nesne [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Özel durumlar hakkında daha fazla bilgi için makalelerine bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="m_sc"></a>  COleException::m_sc  
 Bu veri üyesi özel durumun nedeni gösterir OLE durum kodunu içerir.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değişkenin değerini ayarlamak [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Daha fazla bilgi için `SCODE`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>  COleException::Process  
 Çağrı **işlem** üye işlevi bir OLE durum kodu içine yakalanan bir özel durum çevir.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Parametreler  
 *pAnyException*  
 Yakalanan özel durum işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE durum kodu.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu işlev **statik**.  
  
 Daha fazla bilgi için `SCODE`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CALCDRIV](../../visual-cpp-samples.md)   
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



