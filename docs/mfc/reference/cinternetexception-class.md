---
title: CInternetException Sınıf
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: b0239afa2b984ccf93d661ec11f11013c89fd912
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372414"
---
# <a name="cinternetexception-class"></a>CInternetException Sınıf

Bir Internet çalışmasıyla ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CInternetException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|Bir `CInternetException` nesne inşa eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|Özel durumlara neden olan işlemle ilişkili bağlam değeri.|
|[CInternetException::m_dwError](#m_dwerror)|Özel duruma neden hata.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CInternetException` iki ortak veri üyesi içerir: biri özel durumla ilişkili hata kodunu, diğeri ise hatayla ilişkili Internet uygulamasının bağlam tanımlayıcısını tutar.

Internet uygulamaları için bağlam tanımlayıcıları hakkında daha fazla bilgi için [WinInet ile](../../mfc/win32-internet-extensions-wininet.md)makale Internet Programlama bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a>CInternetException::CInternetException

Bir `CInternetException` nesne oluşturulduğunda bu üye işlev çağrılır.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parametreler

*dwHata*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

CInternetException atmak için, MFC global işlevi [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)arayın.

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a>CInternetException::m_dwContext

İlgili Internet işlemiyle ilişkili bağlam değeri.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Açıklamalar

Bağlam tanımlayıcısı başlangıçta [CInternetSession'da](../../mfc/reference/cinternetsession-class.md) belirtilir ve MFC tarafından [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)'a ve [CInternetFile](../../mfc/reference/cinternetfile-class.md)türetilmiş sınıflara geçirilir. Bu varsayılan geçersiz kılmak ve herhangi bir *dwContext* parametre seçtiğiniz bir değer atayabilirsiniz. *dwContext* verilen nesnenin herhangi bir işlemi ile ilişkilidir. *dwContext,* CInternetSession tarafından döndürülen operasyonun durum bilgilerini [tanımlar::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a>CInternetException::m_dwError

Özel duruma neden hata.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Açıklamalar

Bu hata değeri WINERROR'ta bulunan bir sistem hata kodu olabilir. H veya WININET'ten bir hata değeri. H.

Win32 hata kodlarılistesi için [Hata Kodları'na](/windows/win32/Debug/system-error-codes)bakın. Internet'e özgü hata iletilerinin listesi için bkz. Her iki konu da Windows SDK'da bulunmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
