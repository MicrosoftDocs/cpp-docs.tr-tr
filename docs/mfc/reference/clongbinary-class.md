---
description: 'Daha fazla bilgi edinin: CLongBinary sınıfı'
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
ms.openlocfilehash: ad6836ce6ee7e95929f69d226dcab61fc5482277
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336718"
---
# <a name="clongbinary-class"></a>CLongBinary sınıfı

Bir veritabanında çok büyük ikili veri nesneleriyle (genellikle BLOB veya "ikili büyük nesneler" olarak adlandırılır) çalışmayı basitleştirir.

## <a name="syntax"></a>Syntax

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
|[CLongBinary:: m_dwDataLength](#m_dwdatalength)|Tutamacı içinde depolanan veri nesnesinin bayt cinsinden gerçek boyutunu içerir `m_hData` .|
|[CLongBinary:: m_hData](#m_hdata)|Gerçek görüntü nesnesi için bir Windows HGLOBAL tanıtıcısı içerir.|

## <a name="remarks"></a>Açıklamalar

Örneğin, bir SQL tablosundaki kayıt alanı bir resmi temsil eden bir bit eşlem içerebilir. Bir nesne `CLongBinary` böyle bir nesneyi depolar ve boyutunu izler.

> [!NOTE]
> Genel olarak, şimdi [DFX_Binary](record-field-exchange-functions.md#dfx_binary) Işleviyle birlikte [CByteArray](../../mfc/reference/cbytearray-class.md) 'yi kullanmak daha iyi bir uygulamadır. Yine de kullanabilirsiniz `CLongBinary` , ancak `CByteArray` 16 bit ile karşılaşılan boyut sınırlaması artık bulunmadığından, genel olarak Win32 altında daha fazla işlevsellik sağlar `CByteArray` . Bu öneri, veri erişim nesneleri (DAO) ve açık veritabanı bağlantısı (ODBC) ile programlama için geçerlidir.

Bir nesnesi kullanmak için `CLongBinary` , `CLongBinary` kayıt kümesi sınıfınıza türünde bir alan veri üyesi bildirin. Bu üye, kayıt kümesi sınıfının gömülü bir üyesi olacak ve kayıt kümesi oluşturulduğunda oluşturulacak. Nesne oluşturulduktan sonra `CLongBinary` , kayıt alanı değişimi (RFX) mekanizması veri nesnesini, veri kaynağındaki geçerli kayıttaki bir alandan yükler ve kayıt güncelleştirilirken onu kayda geri kaydeder. RFX, veri kaynağını ikili büyük nesnenin boyutu için sorgular, depolama alanını ( `CLongBinary` nesnenin `m_hData` veri üyesi aracılığıyla) ayırır ve `HGLOBAL` içindeki verilere bir tanıtıcı depolar `m_hData` . RFX Ayrıca veri üyesinde veri nesnesinin gerçek boyutunu depolar `m_dwDataLength` . `m_hData`Bir Windows tanıtıcıda depolanan verileri işlemek için normalde kullandığınız teknikleri kullanarak nesnedeki verilerle çalışın `HGLOBAL` .

Kayıt kümenizin seçimini kaldırdığınızda, katıştırılmış `CLongBinary` nesne de yok edilir ve yıkıcısı `HGLOBAL` veri tanıtıcısını ayırır.

Büyük nesneler ve kullanımı hakkında daha fazla bilgi için `CLongBinary` bkz. Makaleler [kayıt KÜMESI (ODBC)](../../data/odbc/recordset-odbc.md) ve [kayıt kümesi: büyük veri ÖĞELERI ile çalışma (ODBC)](../../data/odbc/recordset-working-with-large-data-items-odbc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxdb_. h

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a> CLongBinary:: CLongBinary

Bir `CLongBinary` nesnesi oluşturur.

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a> CLongBinary:: m_dwDataLength

Gerçek boyutunu içindeki HGLOBAL tanıtıcıda depolanan verilerin bayt cinsinden depolar `m_hData` .

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Açıklamalar

Bu boyut, veriler için ayrılan bellek bloğunun boyutundan daha küçük olabilir. Ayrılan boyutu almak için Win32 [GlobalSize](/windows/win32/api/winbase/nf-winbase-globalsize) işlevini çağırın.

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a> CLongBinary:: m_hData

Gerçek ikili büyük nesne verilerine bir Windows HGLOBAL tanıtıcısı depolar.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
