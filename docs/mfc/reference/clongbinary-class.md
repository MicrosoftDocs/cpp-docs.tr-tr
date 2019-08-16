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
ms.openlocfilehash: 94666c0d15898e05ae78663a15d86b7d00d5c9c6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505681"
---
# <a name="clongbinary-class"></a>CLongBinary sınıfı

Bir veritabanında çok büyük ikili veri nesneleriyle (genellikle BLOB veya "ikili büyük nesneler" olarak adlandırılır) çalışmayı basitleştirir.

## <a name="syntax"></a>Sözdizimi

```
class CLongBinary : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CLongBinary:: CLongBinary](#clongbinary)|Bir `CLongBinary` nesnesi oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CLongBinary:: m_dwDataLength](#m_dwdatalength)|Tutamacı içinde `m_hData`depolanan veri nesnesinin bayt cinsinden gerçek boyutunu içerir.|
|[CLongBinary:: m_hData](#m_hdata)|Gerçek görüntü nesnesi için bir Windows HGLOBAL tanıtıcısı içerir.|

## <a name="remarks"></a>Açıklamalar

Örneğin, bir SQL tablosundaki kayıt alanı bir resmi temsil eden bir bit eşlem içerebilir. Bir `CLongBinary` nesne böyle bir nesneyi depolar ve boyutunu izler.

> [!NOTE]
>  Genel olarak, artık [DFX_Binary](record-field-exchange-functions.md#dfx_binary) Işleviyle birlikte [CByteArray](../../mfc/reference/cbytearray-class.md) 'yi kullanmak daha iyi bir uygulamadır. Yine de kullanabilirsiniz `CLongBinary`, ancak 16 bit `CByteArray`ile `CByteArray` karşılaşılan boyut sınırlaması artık bulunmadığından, genel olarak Win32 altında daha fazla işlevsellik sağlar. Bu öneri, veri erişim nesneleri (DAO) ve açık veritabanı bağlantısı (ODBC) ile programlama için geçerlidir.

Bir `CLongBinary` nesnesi kullanmak için, kayıt kümesi sınıfınıza türünde `CLongBinary` bir alan veri üyesi bildirin. Bu üye, kayıt kümesi sınıfının gömülü bir üyesi olacak ve kayıt kümesi oluşturulduğunda oluşturulacak. `CLongBinary` Nesne oluşturulduktan sonra, kayıt alanı değişimi (RFX) mekanizması veri nesnesini, veri kaynağındaki geçerli kayıttaki bir alandan yükler ve kayıt güncelleştirilirken onu kayda geri kaydeder. RFX, veri kaynağını ikili büyük nesnenin boyutu için sorgular `CLongBinary` , depolama alanını ( `m_hData` nesnenin veri üyesi aracılığıyla) ayırır ve içindeki `m_hData`verilere bir `HGLOBAL` tanıtıcı depolar. RFX Ayrıca veri üyesinde veri nesnesinin `m_dwDataLength` gerçek boyutunu depolar. Bir Windows `m_hData` `HGLOBAL` tanıtıcıda depolanan verileri işlemek için normalde kullandığınız teknikleri kullanarak nesnedeki verilerle çalışın.

Kayıt kümenizin seçimini kaldırdığınızda, katıştırılmış `CLongBinary` nesne de yok edilir ve yıkıcısı `HGLOBAL` veri tanıtıcısını ayırır.

Büyük nesneler ve kullanımı `CLongBinary`hakkında daha fazla bilgi için bkz. Makaleler [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md) ve [kayıt kümesi: Büyük veri öğeleri ile çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb_. h

##  <a name="clongbinary"></a>CLongBinary:: CLongBinary

Bir `CLongBinary` nesnesi oluşturur.

```
CLongBinary();
```

##  <a name="m_dwdatalength"></a>CLongBinary:: m_dwDataLength

Gerçek boyutunu içindeki `m_hData`HGLOBAL tanıtıcıda depolanan verilerin bayt cinsinden depolar.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Açıklamalar

Bu boyut, veriler için ayrılan bellek bloğunun boyutundan daha küçük olabilir. Ayrılan boyutu almak için Win32 [GlobalSize](/windows/win32/api/winbase/nf-winbase-globalsize) işlevini çağırın.

##  <a name="m_hdata"></a>CLongBinary:: m_hData

Gerçek ikili büyük nesne verilerine bir Windows HGLOBAL tanıtıcısı depolar.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
