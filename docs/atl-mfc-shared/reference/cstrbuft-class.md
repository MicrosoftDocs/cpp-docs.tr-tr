---
title: CStrBufT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43c460d45e0f1ce41cebd463bc3ba6b7f295d9ca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411189"
---
# <a name="cstrbuft-class"></a>CStrBufT sınıfı

Otomatik kaynak Temizleme için bu sınıfın sağladığı `GetBuffer` ve `ReleaseBuffer` çağırır var olan bir `CStringT` nesne.

## <a name="syntax"></a>Sözdizimi

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Parametreler

*TCharType*  
Karakter türü `CStrBufT` sınıfı. Aşağıdakilerden biri olabilir:

- **char** (için ANSI karakter dizeleri)

- **wchar_t** (için Unicode karakter dizeleri)

- TCHAR (için ANSI hem Unicode karakter dizeleri)

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|PCXSTR|Bir sabit dize işaretçisi.|
|PXSTR|Bir dizeye bir işaretçi.|
|`StringType`|Bu sınıf şablonu uzmanlıklarıyla yönetilebilmesini, arabellek olan dize türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|Dize arabellek nesnesi için oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT::SetLength](#setlength)|Karakter arabelleği uzunluğu ilişkilendirilmiş dize nesnesine ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Alır bir **const** ilişkili dize nesnesinin karakter arabellek için işaretçi.|
|[CStrBufT::operator PXSTR](#operator_pxstr)|Karakter arabelleği ilişkilendirilmiş dize nesnesine bir işaretçi alır.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|Otomatik olarak yeni sürümde bir dizenin uzunluğunu belirler.|
|[CStrBufT::SET_LENGTH](#set_length)|Dize nesnesi uzunluğunu GetBuffer zamanında ayarlama|

## <a name="remarks"></a>Açıklamalar

Bu sınıf çağrıları değiştirme için bir sarmalayıcı sınıf olarak kullanılan [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), veya [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) ve `ReleaseBuffer`.

Öncelikle bir yardımcı sınıfı tasarlanmış `CStrBufT` hakkında endişelenmeden dizenin başlangıcının karakter arabelleği ile çalışmak bir geliştirici için kolay bir yol sağlar veya çağrısı yapıldığında `ReleaseBuffer`. Sarmalayıcı nesnesine doğal olarak bir özel durum ya da birden çok mevcut kod yolları'durumunda kapsam dışında olduğundan, bu mümkündür; dize kaynağı serbest bırakmak yok edici neden oluyor.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpstr.h

##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH

Otomatik olarak yeni sürümde bir dizenin uzunluğunu belirler.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Açıklamalar

Otomatik olarak yeni sürümde bir dizenin uzunluğunu belirler. Null ile sonlandırılmış bir dize olmalıdır.

##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT

Arabellek bir nesne oluşturur.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Parametreler

*str*  
Arabellek ile ilişkili dize nesnesi. Genellikle, geliştirici, önceden tanımlanmış tür tanımları kullanırsınız `CStrBuf` (TCHAR değişken) `CStrBufA` (**char** değişken) ve `CStrBufW` (**wchar_t** değişken).

*nMinLength*  
En düşük karakter arabelleği uzunluğu.

*CertOpenStore*  
Dize uzunluğu otomatik olarak belirlenen belirler. Aşağıdakilerden biri olabilir:

- AUTO_LENGTH dize uzunluğu, otomatik olarak belirlenen zaman [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) çağrılır. Null ile sonlandırılmış bir dize olmalıdır. Varsayılan değer.

- SET_LENGTH dize uzunluğu ne zaman ayarlanır [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) çağrılır.

### <a name="remarks"></a>Açıklamalar

Dize arabellek için ilişkilendirilmiş dize nesnesi oluşturur. Oluşturma sırasında [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) veya [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) çağrılır.

Kopya Oluşturucu olduğuna dikkat edin **özel**.

##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR

C stili dize olarak ilişkili dize nesnede depolanan karakter doğrudan erişir.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin veri karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizenin başlangıcının karakter arabelleği için bir işaretçiyi döndürmek için bu işlevi çağırın. Bu işaretçiyle içeriğini bir dize nesnesi değiştirilemez.

##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR

C stili dize olarak ilişkili dize nesnede depolanan karakter doğrudan erişir.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizenin veri karakter işaretçisi.

### <a name="remarks"></a>Açıklamalar

Dizenin başlangıcının karakter arabelleği için bir işaretçiyi döndürmek için bu işlevi çağırın. Geliştirici, bu işaretçi ile dize nesnenin içeriğini değiştirebilir.

##  <a name="pcxstr"></a>  CStrBufT::PCXSTR

Bir sabit dize işaretçisi.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

##  <a name="pxstr"></a>  CStrBufT::PXSTR

Bir dizeye bir işaretçi.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

##  <a name="set_length"></a>  CStrBufT::SET_LENGTH

Dize nesne uzunluğunu ayarlayın `GetBuffer` zaman.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Açıklamalar

Dize nesnesi uzunluğunu GetBuffer zamanında ayarlama.

Belirler [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) ve [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) dize arabellek nesne oluşturulduğunda çağrılır.

##  <a name="setlength"></a>  CStrBufT::SetLength

Karakter arabelleği uzunluğu ayarlar.

```
void SetLength(int nLength);
```

### <a name="parameters"></a>Parametreler

*nLength*  
Yeni dize nesnesinin karakter arabelleği uzunluğu.

> [!NOTE]
>  Oluşturucusunun içinde belirtilen en düşük arabellek uzunluğundan küçük veya buna eşit olmalıdır `CStrBufT`.

### <a name="remarks"></a>Açıklamalar

Arabellek nesne tarafından temsil edilen dizenin uzunluğunu ayarlamak için bu işlevi çağırın.

##  <a name="stringtype"></a>  CStrBufT::StringType

Bu sınıf şablonu uzmanlıklarıyla yönetilebilmesini, arabellek olan dize türü.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Açıklamalar

`TCharType` karakter türü sınıf şablonu özelleştirmek için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)

