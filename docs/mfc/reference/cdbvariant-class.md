---
title: CDBVariant sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27970a7d3854dca398943bfe13c67f6a4e1f92f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdbvariant-class"></a>CDBVariant sınıfı
MFC ODBC sınıfları için bir değişken veri türü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|Oluşturan bir `CDBVariant` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|Temizler `CDBVariant` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|Şu anda depolanan değerin veri türü içeriyor. Türü `DWORD`.|  
  
### <a name="public-union-members"></a>Ortak birleşim üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|Türünde bir değer içeren **BOOL**.|  
|[CDBVariant::m_chVal](#m_chval)|Türünde bir değer içeren `unsigned char`.|  
|[CDBVariant::m_dblVal](#m_dblval)|Türünde bir değer içeren **çift**.|  
|[CDBVariant::m_fltVal](#m_fltval)|Türünde bir değer içeren **float**.|  
|[CDBVariant::m_iVal](#m_ival)|Türünde bir değer içeren **kısa**.|  
|[CDBVariant::m_lVal](#m_lval)|Türünde bir değer içeren **uzun**.|  
|[CDBVariant::m_pbinary](#m_pbinary)|Bir nesne türü için bir işaretçi içeriyor `CLongBinary`.|  
|[CDBVariant::m_pdate](#m_pdate)|Bir nesne türü için bir işaretçi içeriyor **TIMESTAMP_STRUCT**.|  
|[CDBVariant::m_pstring](#m_pstring)|Bir nesne türü için bir işaretçi içeriyor `CString`.|  
|[CDBVariant::m_pstringA](#m_pstringa)|Bir işaretçi bir ASCII depolar [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.|  
|[CDBVariant::m_pstringW](#m_pstringw)|Bir geniş bir işaretçi depolar [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDBVariant` bir taban sınıfı yok.  
  
 `CDBVariant` benzer [COleVariant](../../mfc/reference/colevariant-class.md); ancak, `CDBVariant` OLE kullanmaz. `CDBVariant` Bir değer değerinin veri türü hakkında endişelenmeden depolamanıza olanak sağlar. `CDBVariant` veri türü bir birleşim içinde depolanan geçerli değeri izler.  
  
 Sınıf [CRecordset](../../mfc/reference/crecordset-class.md) yararlanan `CDBVariant` üç üye işlevleri nesneleri: `GetFieldValue`, `GetBookmark`, ve `SetBookmark`. Örneğin, `GetFieldValue` , bir sütundaki verileri dinamik olarak getirilemedi sağlar. Sütunun veri türünü çalışma zamanında bilinmiyor çünkü `GetFieldValue` kullanan bir `CDBVariant` sütunun verileri depolamak için nesne.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDBVariant`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="cdbvariant"></a>  CDBVariant::CDBVariant  
 Bir NULL oluşturur `CDBVariant` nesnesi.  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlar [m_dwType](#m_dwtype) veri üyesini **DBVT_NULL**.  
  
##  <a name="clear"></a>  CDBVariant::Clear  
 Temizlemek için bu üye işlevini çağırın `CDBVariant` nesnesi.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa değerini [m_dwType](#m_dwtype) veri üyesi olduğu **DBVT_DATE**, **DBVT_STRING**, veya **DBVT_BINARY**, **temizleyin**birleşim işaretçi üyesiyle ilişkili belleği serbest bırakır. **Clear** ayarlar `m_dwType` için **DBVT_NULL**.  
  
 `CDBVariant` Yıkıcı çağrıları **Temizle**.  
  
##  <a name="m_boolval"></a>  CDBVariant::m_boolVal  
 Türünde bir değer depolar **BOOL**.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_boolVal** veri üyesi ait bir birleşimi. Erişmeden önce **m_boolVal**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_BOOL**, ardından **m_boolVal** geçerli bir değer içerir; Aksi takdirde erişme **m_boolVal** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_chval"></a>  CDBVariant::m_chVal  
 Türünde bir değer depolar `unsigned char`.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_chVal** veri üyesi ait bir birleşimi. Erişmeden önce **m_chVal**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_UCHAR**, ardından **m_chVal** geçerli bir değer içerir; Aksi takdirde erişme **m_chVal** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_dblval"></a>  CDBVariant::m_dblVal  
 Türünde bir değer depolar **çift**.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_dblVal** veri üyesi ait bir birleşimi. Erişmeden önce **m_dblVal**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_DOUBLE**, ardından **m_dblVal** geçerli bir değer içerir; Aksi takdirde erişme **m_dblVal** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_dwtype"></a>  CDBVariant::m_dwType  
 Veri türü şu anda depolanan değeri bu veri üyeyi içeren `CDBVariant` nesnenin birleşim veri üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu birleşim erişmeden önce değerini denetlemelisiniz `m_dwType` erişmek için hangi birleşim veri üyesi belirlemek için. İçin olası değerler aşağıdaki tabloda listelenmektedir `m_dwType` ve karşılık gelen birleşim veri üyesi.  
  
|m_dwType|Birleşim veri üyesi|  
|---------------|-----------------------|  
|**DBVT_NULL**|Hiçbir bileşim üyesi erişim için geçerli değil.|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>  CDBVariant::m_fltVal  
 Türünde bir değer depolar **float**.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_fltVal** veri üyesi ait bir birleşimi. Erişmeden önce **m_fltVal**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_SINGLE**, ardından **m_fltVal** geçerli bir değer içerir; Aksi takdirde erişme **m_fltVal** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_ival"></a>  CDBVariant::m_iVal  
 Türünde bir değer depolar **kısa**.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_iVal** veri üyesi ait bir birleşimi. Erişmeden önce **m_iVal**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_SHORT**, ardından **m_iVal** geçerli bir değer içerir; Aksi takdirde erişme **m_iVal** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_lval"></a>  CDBVariant::m_lVal  
 Türünde bir değer depolar **uzun**.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_lVal** veri üyesi ait bir birleşimi. Erişmeden önce **m_lVal**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_LONG**, ardından **m_lVal** geçerli bir değer içerir; Aksi takdirde erişme **m_lVal** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_pbinary"></a>  CDBVariant::m_pbinary  
 Bir nesne türü için bir işaretçi depolar [CLongBinary](../../mfc/reference/clongbinary-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 **M_pbinary** veri üyesi ait bir birleşimi. Erişmeden önce **m_pbinary**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_BINARY**, ardından **m_pbinary** geçerli bir işaretçi içeriyor; Aksi takdirde erişme **m_pbinary** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_pdate"></a>  CDBVariant::m_pdate  
 Bir nesne türü için bir işaretçi depolar **TIMESTAMP_STRUCT**.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_pdate** veri üyesi ait bir birleşimi. Erişmeden önce **m_pdate**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_DATE**, ardından **m_pdate** geçerli bir işaretçi içeriyor; Aksi takdirde erişme **m_pdate** güvenilir olmayan sonuçlar oluşturabilir.  
  
 Hakkında daha fazla bilgi için **TIMESTAMP_STRUCT** veri türü, konusuna [C veri türleri](https://msdn.microsoft.com/library/ms714556.aspx) ek d kısmındaki *ODBC Programcının Başvurusu* Windows SDK'sındaki.  
  
##  <a name="m_pstring"></a>  CDBVariant::m_pstring  
 Bir nesne türü için bir işaretçi depolar [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 **M_pstring** veri üyesi ait bir birleşimi. Erişmeden önce **m_pstring**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_STRING**, ardından **m_pstring** geçerli bir işaretçi içeriyor; Aksi takdirde erişme **m_pstring** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_pstringa"></a>  CDBVariant::m_pstringA  
 Bir işaretçi bir ASCII depolar [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_pstringA** veri üyesi ait bir birleşimi. Erişmeden önce **m_pstringA**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_ASTRING**, ardından **m_pstringA** geçerli bir işaretçi içeriyor; Aksi takdirde erişme **m_pstringA** güvenilir olmayan sonuçlar oluşturabilir.  
  
##  <a name="m_pstringw"></a>  CDBVariant::m_pstringW  
 Bir geniş bir işaretçi depolar [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 **M_pstringW** veri üyesi ait bir birleşimi. Erişmeden önce **m_pstringW**, ilk değerini denetleyin [CDBVariant::m_dwType](#m_dwtype). Varsa `m_dwType` ayarlanır **DBVT_WSTRING**, ardından **m_pstringW** geçerli bir işaretçi içeriyor; Aksi takdirde erişme **m_pstringW** güvenilir olmayan sonuçlar oluşturabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
