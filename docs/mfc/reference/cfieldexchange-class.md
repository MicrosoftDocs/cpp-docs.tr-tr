---
title: CFieldExchange sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
dev_langs:
- C++
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bad68253525fd728b67f2e256c48a3edbf48d720
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367067"
---
# <a name="cfieldexchange-class"></a>CFieldExchange sınıfı
Kayıt alanı değişimi (RFX) ve veritabanı sınıfları tarafından kullanılan toplu kayıt alanı değişimi (Toplu RFX) yordamları destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|Geçerli işlem ise sıfır olmayan döndürür güncelleştirilmekte alan türü için uygun.|  
|[CFieldExchange::SetFieldType](#setfieldtype)|Kayıt kümesi veri üyesi türünü belirtir — sütunu veya parametresi — RFX işlevleri tüm aşağıdaki çağrıları tarafından temsil edilen sonraki çağrısı kadar `SetFieldType`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CFieldExchange` bir taban sınıfı yok.  
  
 Özel veri türleri veya ne zaman toplu satır getirme uyguluyorsanız için veri değişimi rutinleri yazıyorsanız, bu sınıfı kullanın; Aksi takdirde, bu sınıfın doğrudan kullanmaz. RFX ve toplu RFX kayıt kümesi nesnenizi alan veri üyeleri ve geçerli kayıt veri kaynağı için karşılık gelen alanları arasında veri değiş tokuş eder.  
  
> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, bir sınıf kullanma [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) yerine. Daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 A `CFieldExchange` nesnesi sağlar bağlam bilgisi kayıt alanı değişimi veya yapılacak toplu kayıt alanı değişimi için yerleştirin. `CFieldExchange` nesneleri bir dizi bağlama parametreleri ve alan veri üyeleri de dahil olmak üzere ve geçerli kayıt alanlarını üzerinde çeşitli bayrakları ayarlama işlemi destekler. Kayıt kümesi sınıfı verileri üyeleri tarafından tanımlanan türleri üzerinde gerçekleştirilen RFX ve toplu RFX işlemler `enum` **FieldType** içinde `CFieldExchange`. Olası **FieldType** değerler şunlardır:  
  
- **CFieldExchange::outputColumn** alan veri üyeleri için.  
  
- **CFieldExchange::inputParam** veya **CFieldExchange::param** giriş parametre veri üyeleri için.  
  
- **CFieldExchange::outputParam** çıkış parametre veri üyeleri için.  
  
- **CFieldExchange::inoutParam** giriş/çıkış parametre veri üyeleri için.  
  
 Sınıfının üye işlevleri ve veri üyelerinin birçoğunu kendi özel RFX rutinleri yazmak için sağlanır. Kullanacağınız `SetFieldType` sık. Daha fazla bilgi için makalelere bakın [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). RFX ve toplu RFX genel işlevler hakkında daha fazla ayrıntı için bkz: [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md) bu başvuru MFC makroları ve genel öğeleri bölümünde.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CFieldExchange`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="isfieldtype"></a>  CFieldExchange::IsFieldType  
 Kendi RFX işlevi yazarsanız, çağrı `IsFieldType` geçerli işlem belirli bir alan veya parametre veri üye türü üzerinde gerçekleştirilen olup olmadığını belirlemek için işlevinizi başındaki (bir **CFieldExchange::outputColumn**, **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, veya **CFieldExchange::inoutParam** ).  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>Parametreler  
 *pnField*  
 Bu parametrede döndürülen alan veya parametre veri üyesi sıralı sayısı. Bu sayı veri üyesinin sırayla karşılık gelen [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) işlevi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli işlem geçerli alan veya parametre türüne gerçekleştirilebiliyorsa sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Varolan RFX işlevleri modelinin izleyin.  
  
##  <a name="setfieldtype"></a>  CFieldExchange::SetFieldType  
 Çağrı ihtiyacınız `SetFieldType` kayıt kümesi sınıfınızın içinde [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) geçersiz kılar.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFieldType`  
 Değerini **enum FieldType**bildirilen `CFieldExchange`, olabilen şunlardan biri:  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>Açıklamalar  
 Alan veri üyeleri için çağırmalısınız `SetFieldType` bir parametresi ile **CFieldExchange::outputColumn**, RFX veya toplu RFX işlevleri yapılan çağrılar tarafından izlenen. Toplu satır getirme uygulanmadı durumunda ClassWizard yerleştirir bu `SetFieldType` sizin için alan eşleme bölümünde çağrı `DoFieldExchange`.  
  
 Kayıt kümesi sınıfınız Parametreleştirme varsa çağırmalıdır `SetFieldType` yeniden, herhangi bir alan eşleme bölümü dışında ardından RFX çağrıları tarafından tüm parametre veri üyeleri için. Her tür parametre veri üyesi kendi sahip olmalıdır `SetFieldType` çağırın. Aşağıdaki tabloda farklı değerler için iletebilir ayırt `SetFieldType` sınıfınızın parametre veri üyeleri temsil etmek için:  
  
|SetFieldType parametre değeri|Tür parametresi veri üyesi|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|Giriş parametresi. Kayıt kümesinin sorgu veya saklı yordam içinde geçirilen bir değer.|  
|**CFieldExchange::param**|Aynı **CFieldExchange::inputParam**.|  
|**CFieldExchange::outputParam**|Çıktı parametresi. Kayıt kümesinin saklı yordam dönüş değeri.|  
|**CFieldExchange::inoutParam**|Giriş/çıkış parametresi. İçine aktarılan ve kayıt kümesinin bir saklı yordamdan döndürülen değer.|  
  
 RFX işlev çağrılarını alan veri üyeleri veya parametre veri üyeleri ile ilişkili her grup için bir çağrı tarafından genel olarak, gelmelidir `SetFieldType`. `nFieldType` Her parametre `SetFieldType` çağrısı izleyin RFX işlev çağrıları tarafından temsil edilen veri üyeleri türünü tanımlayan `SetFieldType` çağırın.  
  
 Çıkış ve giriş/çıkış parametreleri işleme hakkında daha fazla bilgi için bkz: `CRecordset` üye işlevi [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). RFX ve toplu RFX işlevleri hakkında daha fazla bilgi için Ek Yardım konusuna [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Toplu satır getirme hakkında ilgili bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
 Bu örnek çağrıları eşlik ile RFX işlevlerini birkaç çağrı gösterilir `SetFieldType`. Unutmayın `SetFieldType` aracılığıyla adlı `pFX` işaretçi bir `CFieldExchange` nesnesi.  
  
 [!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
