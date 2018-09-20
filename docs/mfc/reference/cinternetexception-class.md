---
title: Cınternetexception sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ca7f7a1ea3e1f4738d0837a60e358cf43eebbd8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444188"
---
# <a name="cinternetexception-class"></a>Cınternetexception sınıfı

Bir Internet işlemiyle ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CInternetException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetException::CInternetException](#cinternetexception)|Oluşturur bir `CInternetException` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CInternetException::m_dwContext](#m_dwcontext)|Özel duruma neden işlemle ilişkilendirilen içerik değeri.|
|[CInternetException::m_dwError](#m_dwerror)|Özel duruma neden hata.|

## <a name="remarks"></a>Açıklamalar

`CInternetException` Sınıfı iki genel veri üyeleri içerir: tutan bir özel durumla ilişkili hata kodu ve diğer hatayla ilişkili Internet uygulaması bağlam tanımlayıcısını tutar.

Internet uygulamaları için bağlam tanımlayıcıları hakkında daha fazla bilgi için bkz [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cinternetexception"></a>  CInternetException::CInternetException

Bu üye işlevi aldığında çağrılan bir `CInternetException` nesnesi oluşturulur.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parametreler

*dwError*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

Bir Cınternetexception atmak için MFC genel işlev çağrısı [Afxthrowınternetexception](internet-url-parsing-globals.md#afxthrowinternetexception).

##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext

İlgili Internet işlemle ilişkili içerik değeri.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Açıklamalar

İçerik tanımlayıcısı başlangıçta belirtilen [Cınternetsession](../../mfc/reference/cinternetsession-class.md) ve MFC'ye tarafından geçirilen [Cınternetconnection](../../mfc/reference/cinternetconnection-class.md)- ve [Cınternetfile](../../mfc/reference/cinternetfile-class.md)-türetilmiş sınıflar. Bu varsayılanı geçersiz kılmak ve herhangi bir Ata *dwContext* parametresi, seçtiğiniz bir değer. *dwContext* verilen nesnenin herhangi bir işlem ile ilişkilidir. *dwContext* tarafından döndürülen işlem durumu bilgilerini tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

##  <a name="m_dwerror"></a>  CInternetException::m_dwError

Özel duruma neden hata.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Açıklamalar

Bu hata değeri bir sistem olabilir WINERROR içinde bulunan bir hata kodu. H veya WİNINET gelen bir hata değeri. H

Win32 hata kodlarına listesi için bkz. [hata kodları](/windows/desktop/Debug/system-error-codes). Internet özel hata iletileri bir listesi için bkz. Windows SDK'yı hem konulardır.

## <a name="see-also"></a>Ayrıca Bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
