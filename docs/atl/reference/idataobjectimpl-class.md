---
title: "IDataObjectImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl
- ATLCTL/ATL::IDataObjectImpl::DAdvise
- ATLCTL/ATL::IDataObjectImpl::DUnadvise
- ATLCTL/ATL::IDataObjectImpl::EnumDAdvise
- ATLCTL/ATL::IDataObjectImpl::EnumFormatEtc
- ATLCTL/ATL::IDataObjectImpl::FireDataChange
- ATLCTL/ATL::IDataObjectImpl::GetCanonicalFormatEtc
- ATLCTL/ATL::IDataObjectImpl::GetData
- ATLCTL/ATL::IDataObjectImpl::GetDataHere
- ATLCTL/ATL::IDataObjectImpl::QueryGetData
- ATLCTL/ATL::IDataObjectImpl::SetData
dev_langs:
- C++
helpviewer_keywords:
- data transfer [C++]
- data transfer [C++], Uniform Data Transfer
- IDataObjectImpl class
- IDataObject, ATL implementation
ms.assetid: b680f0f7-7795-40a1-a0f6-f48768201c89
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 644f498a491605fb69b18ec53afee689f5f90a26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idataobjectimpl-class"></a>IDataObjectImpl sınıfı
Bu sınıf Tekdüzen veri aktarımı destekleme ve bağlantıları yönetme için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class IDataObjectImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IDataObjectImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDataObjectImpl::DAdvise](#dadvise)|Veri nesnesi ve bir öneri havuz arasında bir bağlantı kurar. Bu nesne değişiklik bildirimlerini almak üzere öneri havuz sağlar.|  
|[IDataObjectImpl::DUnadvise](#dunadvise)|Üzerinden daha önce oluşturulmuş bir bağlantıyı sonlandırır `DAdvise`.|  
|[IDataObjectImpl::EnumDAdvise](#enumdadvise)|Geçerli danışma bağlantılarında yinelemek için bir numaralandırıcı oluşturur.|  
|[IDataObjectImpl::EnumFormatEtc](#enumformatetc)|Yinelemek için bir numaralandırıcı oluşturur **FORMATETC** veri nesnesi tarafından desteklenen yapıları. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IDataObjectImpl::FireDataChange](#firedatachange)|Bir değişiklik bildirimi her öneri havuz geri gönderir.|  
|[IDataObjectImpl::GetCanonicalFormatEtc](#getcanonicalformatetc)|Mantıksal olarak eşdeğer alır **FORMATETC** daha karmaşık bir yapısı. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IDataObjectImpl::GetData](#getdata)|Verileri veri nesnesinden istemciye aktarır. Veri açıklanan bir **FORMATETC** yapısı ve üzerinden aktarılan bir **STGMEDIUM** yapısı.|  
|[IDataObjectImpl::GetDataHere](#getdatahere)|Benzer şekilde `GetData`, istemci ayırmalısınız dışında **STGMEDIUM** yapısı. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IDataObjectImpl::QueryGetData](#querygetdata)|Veri nesnesi belirli bir destekleyip desteklemediğini belirler **FORMATETC** veri aktarmak için yapısı. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IDataObjectImpl::SetData](#setdata)|Verileri veri nesnesine istemciden aktarır. ATL uygulamasını döndürür **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) arabirimi Tekdüzen veri aktarımı desteklemek için yöntemler sağlar. `IDataObject`standart biçim yapıları kullanan [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) ve [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) veri depolamak ve almak için.  
  
 `IDataObject`Ayrıca veri değişikliği bildirimleri işleme havuzlarını bildirmek için bağlantıları yönetir. İstemci istemcinin veri nesnesinden veri değişikliği bildirimleri almak sırayla uygulamalıdır [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) bir öneri havuz adlı bir nesne üzerinde arabirimi. İstemci ardından çağırdığında **IDataObject::DAdvise**, veri nesnesi ve öneri havuz arasında bir bağlantı oluşturulur.  
  
 Sınıf `IDataObjectImpl` bir varsayılan uygulamayı sağlar `IDataObject` ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IDataObject`  
  
 `IDataObjectImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="dadvise"></a>IDataObjectImpl::DAdvise  
 Veri nesnesi ve bir öneri havuz arasında bir bağlantı kurar.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nesne değişiklik bildirimlerini almak üzere öneri havuz sağlar.  
  
 Bağlantıyı sonlandırmak için çağrı [DUnadvise](#dunadvise).  
  
 Bkz: [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) Windows SDK.  
  
##  <a name="dunadvise"></a>IDataObjectImpl::DUnadvise  
 Üzerinden daha önce oluşturulmuş bir bağlantıyı sonlandırır [DAdvise](#dadvise).  
  
```
HRESULT DUnadvise(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) Windows SDK.  
  
##  <a name="enumdadvise"></a>IDataObjectImpl::EnumDAdvise  
 Geçerli danışma bağlantılarında yinelemek için bir numaralandırıcı oluşturur.  
  
```
HRESULT DAdvise(
    FORMATETC* pformatetc,
    DWORD advf,
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDataObject::EnumDAdvise](http://msdn.microsoft.com/library/windows/desktop/ms680127) Windows SDK.  
  
##  <a name="enumformatetc"></a>IDataObjectImpl::EnumFormatEtc  
 Yinelemek için bir numaralandırıcı oluşturur **FORMATETC** veri nesnesi tarafından desteklenen yapıları.  
  
```
HRESULT EnumFormatEtc(  
    DWORD dwDirection,
    IEnumFORMATETC** ppenumFormatEtc);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows SDK.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
##  <a name="firedatachange"></a>IDataObjectImpl::FireDataChange  
 Şu anda yönetilen geri her öneri havuz için bir değişiklik bildirimi gönderir.  
  
```
HRESULT FireDataChange();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="getcanonicalformatetc"></a>IDataObjectImpl::GetCanonicalFormatEtc  
 Mantıksal olarak eşdeğer alır **FORMATETC** daha karmaşık bir yapısı.  
  
```
HRESULT GetCanonicalFormatEtc(FORMATETC* pformatetcIn, FORMATETC* pformatetcOut);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDataObject::GetCanonicalFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms680685) Windows SDK.  
  
##  <a name="getdata"></a>IDataObjectImpl::GetData  
 Verileri veri nesnesinden istemciye aktarır.  
  
```
HRESULT GetData(
    FORMATETC* pformatetcIn,
    STGMEDIUM* pmedium);
```  
  
### <a name="remarks"></a>Açıklamalar  
 *PformatetcIn* parametresi depolama Orta türü belirtmelisiniz **TYMED_MFPICT**.  
  
 Bkz: [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431) Windows SDK.  
  
##  <a name="getdatahere"></a>IDataObjectImpl::GetDataHere  
 Benzer şekilde `GetData`, istemci ayırmalısınız dışında **STGMEDIUM** yapısı.  
  
```
HRESULT GetDataHere(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms687266) Windows SDK.  
  
##  <a name="querygetdata"></a>IDataObjectImpl::QueryGetData  
 Veri nesnesi belirli bir destekleyip desteklemediğini belirler **FORMATETC** veri aktarmak için yapısı.  
  
```
HRESULT QueryGetData(FORMATETC* pformatetc);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637) Windows SDK.  
  
##  <a name="setdata"></a>IDataObjectImpl::SetData  
 Verileri veri nesnesine istemciden aktarır.  
  
```
HRESULT SetData(
    FORMATETC* pformatetc,
    STGMEDIUM* pmedium,
    BOOL fRelease);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDataObject::SetData](http://msdn.microsoft.com/library/windows/desktop/ms686626) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
