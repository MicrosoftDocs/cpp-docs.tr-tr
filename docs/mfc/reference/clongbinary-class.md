---
title: CLongBinary sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs:
- C++
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f7030fdcb59166c0e70a7b2c2471273c913fe459
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="clongbinary-class"></a>CLongBinary sınıfı
Bir veritabanındaki (genellikle BLOB veya "ikili büyük nesneler" olarak adlandırılır) çok büyük ikili veri nesneleri ile çalışma basitleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|Oluşturan bir `CLongBinary` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Gerçek boyut, tanıtıcı depolanır veri nesnesinin bayt içeren `m_hData`.|  
|[CLongBinary::m_hData](#m_hdata)|Bir Windows içeren `HGLOBAL` işlemek için gerçek Resim nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, bir SQL tablosuna bir kayıt alanda bir resmi temsil eden bir bit eşlem içerebilir. A `CLongBinary` nesne böyle bir nesnenin depolar ve boyutuna izler.  
  
> [!NOTE]
>  Genel olarak, bunu kullanmak için daha iyi şimdi uygulamadır [CLongBinary](../../mfc/reference/cbytearray-class.md) birlikte [DFX_Binary](record-field-exchange-functions.md#dfx_binary) işlevi. Kullanmaya devam edebilirsiniz `CLongBinary`, ancak genel olarak `CByteArray` olduğundan artık 16 bit ile karşılaştı boyutu sınırlaması Win32 altında daha fazla işlevsellik sağlayan `CByteArray`. Bu öneri, açık veritabanı bağlantısı (ODBC) yanı sıra veri erişim nesneleri (DAO) ile programlama için geçerlidir.  
  
 Kullanılacak bir `CLongBinary` nesne türünün bir alan veri üyesi bildirme `CLongBinary` kayıt kümesi sınıfınızda. Bu üye, kayıt kümesi sınıfı katıştırılmış bir üyesi olur ve kayıt oluşturulduğunda oluşturulur. Sonra `CLongBinary` nesne yapılandırılmıştır, kayıt alanı değişimi (RFX) mekanizması geçerli kayıt veri kaynağında bir alandan veri nesnesi yükler ve kayıt güncelleştirildiğinde geri kayda depolar. RFX ikili büyük nesne boyutunu ayırır için depolama birimi için veri kaynağını sorgular (aracılığıyla `CLongBinary` nesnenin `m_hData` veri üyesi) ve depolayan bir `HGLOBAL` işlemek verilerde `m_hData`. RFX veri nesnesinde gerçek boyutuna da depolar `m_dwDataLength` veri üyesi. İş nesnesi aracılığıyla verilerle `m_hData`, normalde kullandığınız Windows depolanan verileri işlemek için aynı teknikleri kullanarak `HGLOBAL` işler.  
  
 Destroy zaman kümenizin, katıştırılmış `CLongBinary` nesne ayrıca yok ve onun yıkıcı kaldırır `HGLOBAL` veri işleyici.  
  
 Büyük nesneler ve kullanımı hakkında daha fazla bilgi için `CLongBinary`, makalelerine bakın [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md) ve [kayıt kümesi: büyük veri öğeleri (ODBC) ile çalışmaya](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb_.h  
  
##  <a name="clongbinary"></a>  CLongBinary::CLongBinary  
 Oluşturan bir `CLongBinary` nesnesi.  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>  CLongBinary::m_dwDataLength  
 Gerçek boyutu bayt depolanan veri depolar `HGLOBAL` içinde işlemek `m_hData`.  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu boyut veri için ayrılan bellek bloğu boyutundan küçük olabilir. Win32 çağrısı [GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593) ayrılmış boyutu almak için işlevi.  
  
##  <a name="m_hdata"></a>  CLongBinary::m_hData  
 Bir Windows depolar `HGLOBAL` işlemek için gerçek ikili büyük nesne veri.  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
