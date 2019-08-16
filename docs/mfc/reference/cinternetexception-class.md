---
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
ms.openlocfilehash: c4f4c7a5b7594270aff9dfbc224e9a66ba09be3f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505914"
---
# <a name="cinternetexception-class"></a>CInternetException Sınıfı

Bir Internet işlemiyle ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

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

`CInternetException` Sınıfı iki ortak veri üyesi içerir: biri özel durumla ilişkili hata kodunu barındırır ve diğeri hatayla ilişkili Internet uygulamasının bağlam tanımlayıcısını barındırır.

Internet uygulamalarına yönelik bağlam tanımlayıcıları hakkında daha fazla bilgi için bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

##  <a name="cinternetexception"></a>CInternetException:: CInternetException

Bu üye işlevi, bir `CInternetException` nesne oluşturulduğunda çağrılır.

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>Parametreler

*dwError*<br/>
Özel duruma neden hata.

### <a name="remarks"></a>Açıklamalar

CInternetException oluşturmak için, [AFXTHROWıNTERNETEXCEPTION](internet-url-parsing-globals.md#afxthrowinternetexception)MFC genel işlevini çağırın.

##  <a name="m_dwcontext"></a>CInternetException:: m_dwContext

İlgili Internet işlemiyle ilişkili bağlam değeri.

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>Açıklamalar

Bağlam tanımlayıcısı başlangıçta [CInternetSession](../../mfc/reference/cinternetsession-class.md) 'da BELIRTILIR ve MFC tarafından [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)-ve [CInternetFile](../../mfc/reference/cinternetfile-class.md)ile türetilmiş sınıflara geçirilir. Bu varsayılanı geçersiz kılabilir ve seçtiğiniz bir değer için herhangi bir *dwContext* parametresini atayabilirsiniz. *dwContext* , belirtilen nesnenin herhangi bir işlemiyle ilişkili. *dwContext* , [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)tarafından döndürülen işlemin durum bilgilerini tanımlar.

##  <a name="m_dwerror"></a>CInternetException:: m_dwError

Özel duruma neden hata.

```
DWORD m_dwError;
```

### <a name="remarks"></a>Açıklamalar

Bu hata değeri, WINERROR 'da bulunan bir sistem hata kodu olabilir. H veya WININET 'den bir hata değeri. Olsun.

Win32 hata kodlarının listesi için bkz. [hata kodları](/windows/win32/Debug/system-error-codes). Internet 'e özgü hata iletilerinin listesi için bkz. Her iki konu de Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
