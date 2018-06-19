---
title: CArchiveException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac864831e9d3a0cf0cd5e67501f1ac8396f99473
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352612"
---
# <a name="carchiveexception-class"></a>CArchiveException sınıfı
Bir seri hale getirme özel durumu temsil eder  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CArchiveException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](#carchiveexception)|Oluşturan bir `CArchiveException` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CArchiveException::m_cause](#m_cause)|Özel durum nedenini gösterir.|  
|[CArchiveException::m_strFileName](#m_strfilename)|Bu özel durum için dosya adını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CArchiveException` Sınıfı, özel durum nedenini belirten bir genel veri üyesi içerir.  
  
 `CArchiveException` nesneleri oluşturulur ve içinde oluşturulan [CArchive](../../mfc/reference/carchive-class.md) üye işlevleri. Bu nesneler kapsamında erişim bir **CATCH** ifade. Neden kodu işletim sistemini bağımsızdır. Özel durum işleme hakkında daha fazla bilgi için bkz: [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException  
 Oluşturan bir `CArchiveException` değerini depolama nesnesi `cause` nesnesindeki.  
  
```  
CArchiveException(
    int cause = CArchiveException::none,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `cause`  
 Özel durumun nedeni gösteren bir Enum Türü değişkeni. Numaralandırmalar bir listesi için bkz: [m_cause](#m_cause) veri üyesi.  
  
 `lpszArchiveName`  
 İşaret adını içeren bir dize `CArchive` özel duruma neden nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturabileceğiniz bir `CArchiveException` nesne öbek üzerinde ve kendiniz throw veya genel işlevi izin [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) sizin için yapar.  
  
 Bu oluşturucu doğrudan kullanmayın; Bunun yerine, genel bir işlevi çağırmak `AfxThrowArchiveException`.  
  
##  <a name="m_cause"></a>  CArchiveException::m_cause  
 Özel durum nedenini belirtir.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu veri üyesi tür genel bir değişkendir `int`. Değerlerini tarafından tanımlanan bir `CArchiveException` numaralandırılmış türü. Numaralandırmalar ve anlamları şu şekildedir:  
  
- **CArchiveException::none** herhangi bir hata oluştu.  
  
- **CArchiveException::genericException** belirtilmeyen hata.  
  
- **CArchiveException::readOnly** yükleme için açılan bir arşivde içine yazmaya çalıştı.  
  
- **CArchiveException::endOfFile** ulaşıldı bir nesne okunurken dosya sonu.  
  
- **CArchiveException::writeOnly** depolamak için açılan bir arşivde okuma çalışıldı.  
  
- **CArchiveException::badIndex** dosya biçimi geçersiz.  
  
- **CArchiveException::badClass** yanlış türde bir nesneye bir nesne okumak için çalıştı.  
  
- **CArchiveException::badSchema** sınıfının farklı bir sürümünü içeren bir nesne okumak için çalıştı.  
  
    > [!NOTE]
    >  Bunlar `CArchiveException` neden numaralandırıcılar ayrı `CFileException` numaralandırıcılar neden.  
  
    > [!NOTE]
    > **CArchiveException::generic** kullanım dışı bırakılmıştır. Kullanım **genericException** yerine. Varsa **genel** bir uygulamada kullanılan ve yerleşik/CLR ile olacaktır geçirilirse kolay olmayan sözdizimi hataları.  
  
##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName  
 Bu özel durum için dosya adını belirtir.  
  
```  
CString m_strFileName;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CArchive sınıfı](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)   
 [Özel Durum İşleme](../../mfc/reference/exception-processing.md)

