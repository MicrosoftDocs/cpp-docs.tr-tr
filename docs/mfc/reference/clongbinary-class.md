---
title: CLongBinary sınıfı
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: ed3a153ec89785a9c9da43037d20f7d88b5661ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225208"
---
# <a name="clongbinary-class"></a>CLongBinary sınıfı

Veritabanındaki (genellikle BLOB veya "büyük ikili nesneler" olarak adlandırılır) çok büyük ikili veri nesnelerle çalışmayı kolaylaştırır.

## <a name="syntax"></a>Sözdizimi

```
class CLongBinary : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CLongBinary::CLongBinary](#clongbinary)|Oluşturur bir `CLongBinary` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Gerçek boyut, tanıtıcı depolanan veri nesnesinin bayt cinsinden içeren `m_hData`.|
|[CLongBinary::m_hData](#m_hdata)|Gerçek görüntü nesnesi için bir Windows HGLOBAL tanıtıcı içerir.|

## <a name="remarks"></a>Açıklamalar

Örneğin, bir SQL tablosuna bir kayıt alan bir resmi temsil eden bir bit eşlem içerebilir. A `CLongBinary` nesne, böyle bir nesne depolar ve boyutunu izler.

> [!NOTE]
>  Genel olarak, bunu kullanmak için daha iyi artık uygulamadır [CByteArray](../../mfc/reference/cbytearray-class.md) birlikte [DFX_Binary](record-field-exchange-functions.md#dfx_binary) işlevi. Kullanmaya devam edebilirsiniz `CLongBinary`, ancak genel `CByteArray` olduğundan artık, 16-bit ile karşılaştı boyutuna sınırlama Win32 altında daha fazla işlevsellik sağlayan `CByteArray`. Bu öneri, programlama açık veritabanı bağlantısı (ODBC) yanı sıra veri erişim nesneleri (DAO) için geçerlidir.

Kullanılacak bir `CLongBinary` nesnesi alan veri üyesi türünün bildirmek `CLongBinary` kayıt kümesi sınıfınızda. Bu üye, gömülü bir kayıt kümesi sınıfının üyesi olacak ve kayıt oluşturulduğunda oluşturulur. Sonra `CLongBinary` nesnesi oluşturulduğunda, kayıt alanı değişimi (RFX) mekanizması bir alandaki geçerli kayıt veri kaynağı için veri nesnesi yükler ve kayıt güncelleştirildiğinde kayda depolar. RFX ikili büyük nesne boyutu ayırdığı için depolama için veri kaynağını sorgular (aracılığıyla `CLongBinary` nesnenin `m_hData` veri üyesi) ve depolayan bir `HGLOBAL` verileri tanıtıcı `m_hData`. RFX veri nesnesinde gerçek boyutuna da depolar `m_dwDataLength` veri üyesi. İş nesnesi üzerinden verilerle `m_hData`, normalde kullandığınız bir Windows içinde depolanan verileri işlemek için aynı teknikleri kullanarak `HGLOBAL` tanıtıcı.

Yok, kayıt, katıştırılmış `CLongBinary` nesne de yok edilir ve yok edici kaldırır `HGLOBAL` veri işleyici.

Büyük nesneler ve kullanımı hakkında daha fazla bilgi için `CLongBinary`, makalelere göz atın [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md) ve [kayıt kümesi: Büyük veri öğeleri ile çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb_.h

##  <a name="clongbinary"></a>  CLongBinary::CLongBinary

Oluşturur bir `CLongBinary` nesne.

```
CLongBinary();
```

##  <a name="m_dwdatalength"></a>  CLongBinary::m_dwDataLength

Gerçek Boyut HGLOBAL tutamacın depolanan verileri baytlık depolar `m_hData`.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Açıklamalar

Bu büyüklükteki veriler için ayrılan bellek blok boyutundan daha küçük olabilir. Win32 çağrı [GLobalSize](/windows/desktop/api/winbase/nf-winbase-globalsize) ayrılmış boyutunu almak için işlevi.

##  <a name="m_hdata"></a>  CLongBinary::m_hData

Windows HGLOBAL işleyici gerçek ikili büyük nesne verilerini depolar.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
