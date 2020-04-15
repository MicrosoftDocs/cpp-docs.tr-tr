---
title: CLongBinary Sınıfı
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
ms.openlocfilehash: 1ce1daba90f3a1dad4b9627082d63f1b3405eab4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370132"
---
# <a name="clongbinary-class"></a>CLongBinary Sınıfı

Veritabanında çok büyük ikili veri nesneleri (genellikle BLOB sadıyla veya "ikili büyük nesneler" olarak adlandırılır) çalışmayı kolaylaştırır.

## <a name="syntax"></a>Sözdizimi

```
class CLongBinary : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CLongBinary::CLongBinary](#clongbinary)|Bir `CLongBinary` nesne inşa eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|Tanıtıcısı ' nda depolanan veri nesnesinin baytlarında gerçek boyutunu `m_hData`içerir.|
|[CLongBinary::m_hData](#m_hdata)|Gerçek görüntü nesnesine bir Windows HGLOBAL tutamacı içerir.|

## <a name="remarks"></a>Açıklamalar

Örneğin, BIR SQL tablosundaki kayıt alanı, bir resmi temsil eden bir bit eşlemi içerebilir. Bir `CLongBinary` nesne böyle bir nesneyi saklar ve boyutunu izler.

> [!NOTE]
> Genel olarak, [DFX_Binary](record-field-exchange-functions.md#dfx_binary) fonksiyonu ile birlikte [CByteArray](../../mfc/reference/cbytearray-class.md) kullanmak şimdi daha iyi bir uygulamadır. Hala kullanabilirsiniz `CLongBinary`, ama `CByteArray` genel olarak Win32 altında daha fazla işlevsellik sağlar, artık `CByteArray`16-bit ile karşılaşılan boyut sınırlaması olduğundan. Bu öneri, Veri Erişim Nesneleri (DAO) yanı sıra Açık Veritabanı Bağlantısı (ODBC) ile programlama için geçerlidir.

Bir `CLongBinary` nesneyi kullanmak için, kayıt `CLongBinary` kümesi sınıfınızda bir alan veri üyesi yazın bildirin. Bu üye, kayıt kümesi sınıfının gömülü bir üyesi olacak ve kayıt kümesi oluşturulduğunda oluşturulacaktır. `CLongBinary` Nesne oluşturulduktan sonra, kayıt alanı değişimi (RFX) mekanizması veri kaynağındaki geçerli kayıttaki bir alandaki veri nesnesini yükler ve kayıt güncelleştirildiğinde kayda geri depolar. RFX, ikili büyük nesnenin boyutu için veri kaynağını sorgular, bunun `CLongBinary` için `m_hData` depolama alanı ayırır `HGLOBAL` (nesnenin veri `m_hData`üyesi aracılığıyla) ve veri için bir tutamacı depolar. RFX ayrıca `m_dwDataLength` veri üyesinde veri nesnesinin gerçek boyutunu depolar. Windows `HGLOBAL` tanıtıcısında depolanan `m_hData`verileri işlemek için normalde kullanacağınız teknikleri kullanarak nesnedeki verilerle çalışın.

Kayıt setinizi yok ettiğinizde, `CLongBinary` katıştırılmış nesne de yok edilir ve `HGLOBAL` onun imha edicisi veri tutamacını yerle bir eder.

Büyük nesneler ve kullanımı hakkında daha `CLongBinary`fazla bilgi için, kayıt [seti (ODBC)](../../data/odbc/recordset-odbc.md) ve [Recordset: Büyük Veri Öğeleri (ODBC) ile çalışma](../../data/odbc/recordset-working-with-large-data-items-odbc.md)makalelerine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb_.h

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a>CLongBinary::CLongBinary

Bir `CLongBinary` nesne inşa eder.

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength

HGLOBAL tanıtıcısında depolanan verilerin gerçek boyutunu baytlarda `m_hData`depolar.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>Açıklamalar

Bu boyut, veriler için ayrılan bellek bloğunun boyutundan küçük olabilir. Ayrılan boyutu elde etmek için Win32 [GLobalSize](/windows/win32/api/winbase/nf-winbase-globalsize) işlevini arayın.

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a>CLongBinary::m_hData

Bir Windows HGLOBAL tutamacını gerçek ikili büyük nesne verilerine depolar.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
