---
title: "CSimpleException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs: C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d7730fdd356b8145b771a85b8449974c2c8fa007
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimpleexception-class"></a>CSimpleException sınıfı
Bu sınıf, kaynak kritik MFC özel durumlar için temel bir sınıftır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Gerçekleşen hata ile ilgili metin sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSimpleException`Kaynak kritik MFC özel durumlar için temel sınıfı olan ve bir hata iletisi, başlatma ve sahipliği işler. Aşağıdaki sınıflar kullanım `CSimpleException` temel sınıf olarak:  
  
|||  
|-|-|  
|[CMemoryException Sınıfı](../../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz özel durumu|  
|[CNotSupportedException Sınıfı](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem için istekleri|  
|[CResourceException Sınıfı](../../mfc/reference/cresourceexception-class.md)|Windows kaynak bulunamadı veya yok creatable|  
|[CUserException Sınıfı](../../mfc/reference/cuserexception-class.md)|Bir kaynak gösteren özel durumu bulunamadı.|  
|[CInvalidArgException Sınıfı](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bağımsız değişken gösteren özel durumu|  
  
 Çünkü `CSimpleException` , bildiremezsiniz bir Özet temel sınıf olan bir `CSimpleException` doğrudan nesne. Bunun yerine, önceki tabloda bulunanlar gibi türetilen nesneleri bildirmeniz gerekir. Kendi türetilmiş bir sınıf bildirme, önceki sınıfları model olarak kullanın.  
  
 Daha fazla bilgi için bkz: [CException sınıfı](../../mfc/reference/cexception-class.md) konu ve [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="csimpleexception"></a>CSimpleException::CSimpleException  
 Oluşturucu.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Parametreler  
 `bAutoDelete`  
 Belirtin **TRUE** varsa için bellek `CSimpleException` nesne öbek üzerinde ayrıldı. Bu neden olacak `CSimpleException` zaman Silinecek nesnenin **silmek** üye işlevi, özel durum silmek için çağrılır. Belirtin **FALSE** varsa `CSimpleException` nesne yığında veya genel bir nesnedir. Bu durumda, `CSimpleException` nesne olmayacak ne zaman silinmiş **silmek** üye işlevi çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Normalde hiçbir zaman bu oluşturucu doğrudan çağırmanız gerekir. Bir özel durum oluşturur işlevi bir örneğini oluşturmanız gerekir bir `CException`-türetilmiş sınıf ve MFC'nin kullanım throw işlevleri gibi kurucusu veya çağrı [AfxThrowFileException](exception-processing.md#afxthrowfileexception), önceden tanımlanmış bir türü atmak için.  
  
##  <a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
 Gerçekleşen hata ile ilgili metin sağlamak için bu üye işlevini çağırın.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszError`  
 Bir hata iletisi alırsınız bir arabellek için bir işaretçi.  
  
 `nMaxError`  
 En fazla arabellek tut dahil olmak üzere karakter sayısını **NULL** Sonlandırıcı.  
  
 `pnHelpContext`  
 Adresini bir **UINT** Yardım bağlam kimliğini alacaksınız Varsa **NULL**, kimliği yok döndürülür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılıysa sıfır olmayan; Aksi takdirde metin hata iletisini yoksa 0 kullanılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Özel Durum İşleme](../../mfc/exception-handling-in-mfc.md)



