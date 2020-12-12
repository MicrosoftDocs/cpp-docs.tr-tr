---
description: 'Daha fazla bilgi edinin: CInternetException Sınıfı'
title: CInternetException Sınıfı
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
ms.openlocfilehash: d46c2eca7f7f568b0296d6ced567d33b49ba4cb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209951"
---
# <a name="cinternetexception-class"></a>CInternetException Sınıfı

Bir Internet işlemiyle ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```
class CInternetException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetException:: CInternetException](#cinternetexception)|Bir `CInternetException` nesnesi oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CInternetException:: m_dwContext](#m_dwcontext)|Özel duruma neden olan işlemle ilişkili bağlam değeri.|
|[CInternetException:: m_dwError](#m_dwerror)|Özel duruma neden hata.|

## <a name="remarks"></a>Açıklamalar

`CInternetException`Sınıfı iki ortak veri üyesi içerir: biri özel durumla ilişkili hata kodunu barındırır ve diğeri hatayla Ilişkili Internet uygulamasının bağlam tanımlayıcısını barındırır.

Internet uygulamalarına yönelik bağlam tanımlayıcıları hakkında daha fazla bilgi için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a> CInternetException:: CInternetException

Bu üye işlevi, bir `CInternetException` nesne oluşturulduğunda çağrılır.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parametreler

*dwError*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

CInternetException oluşturmak için, [AFXTHROWıNTERNETEXCEPTION](internet-url-parsing-globals.md#afxthrowinternetexception)MFC genel işlevini çağırın.

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a> CInternetException:: m_dwContext

İlgili Internet işlemiyle ilişkili bağlam değeri.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Açıklamalar

Bağlam tanımlayıcısı başlangıçta [CInternetSession](../../mfc/reference/cinternetsession-class.md) 'da BELIRTILIR ve MFC tarafından [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)-ve [CInternetFile](../../mfc/reference/cinternetfile-class.md)ile türetilmiş sınıflara geçirilir. Bu varsayılanı geçersiz kılabilir ve seçtiğiniz bir değer için herhangi bir *dwContext* parametresini atayabilirsiniz. *dwContext* , belirtilen nesnenin herhangi bir işlemiyle ilişkili. *dwContext* , [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)tarafından döndürülen işlemin durum bilgilerini tanımlar.

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a> CInternetException:: m_dwError

Özel duruma neden hata.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Açıklamalar

Bu hata değeri, WINERROR 'da bulunan bir sistem hata kodu olabilir. Ya da WININET. H öğesinden bir hata değeri.

Win32 hata kodlarının listesi için bkz. [hata kodları](/windows/win32/Debug/system-error-codes). Internet 'e özgü hata iletilerinin listesi için bkz.. Her iki konu de Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)
