---
title: CAtlFileMappingBase Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: 75177c195e83a4ab3ad2a6bd4d608d07f8c2234f
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168091"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase Sınıfı

Bu sınıf, bellek eşlemeli bir dosyayı temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
class CAtlFileMappingBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase:: CAtlFileMappingBase](#catlfilemappingbase)|Oluşturucu.|
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase:: CopyFrom](#copyfrom)|Dosya eşleme nesnesinden kopyalamak için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: GetData](#getdata)|Bir dosya eşleme nesnesinden verileri almak için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: GetHandle](#gethandle)|Dosya tanıtıcısını döndürmek için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: GetMappingSize](#getmappingsize)|Bir dosya eşleme nesnesinden eşleme boyutunu almak için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: MapFile](#mapfile)|Dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: MapSharedMem](#mapsharedmem)|Tüm işlemlere tam erişime izin veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: OpenMapping](#openmapping)|Dosya eşleme nesnesine bir tanıtıcı döndürmek için bu yöntemi çağırın.|
|[CAtlFileMappingBase:: eşlemesini Kaldır](#unmap)|Dosya eşleme nesnesinin eşlemesini kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase:: operator =](#operator_eq)|Geçerli dosya eşleme nesnesini başka bir dosya eşleme nesnesi olarak ayarlar.|

## <a name="remarks"></a>Açıklamalar

Dosya eşleme, bir dosyanın içeriğinin bir işlemin sanal adres alanının bir bölümüyle ilişkilendirilmesi. Bu sınıf, programların verilere kolayca erişip paylaşmasına izin veren dosya eşleme nesneleri oluşturmak için yöntemler sağlar.

Daha fazla bilgi için Windows SDK [dosya eşleme](/windows/win32/Memory/file-mapping) konusuna bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile. h

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>CAtlFileMappingBase:: CAtlFileMappingBase

Oluşturucu.

```cpp
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>Parametreler

*cumg*<br/>
Yeni nesneyi oluşturmak için kopyalanacak özgün dosya eşleme nesnesi.

### <a name="remarks"></a>Açıklamalar

İsteğe bağlı olarak, var olan bir nesneyi kullanarak yeni bir dosya eşleme nesnesi oluşturur. Belirli bir dosya için dosya eşleme nesnesini açmak veya oluşturmak üzere [CAtlFileMappingBase:: MapFile](#mapfile) çağrısı yapmak yine de gereklidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>CAtlFileMappingBase:: ~ CAtlFileMappingBase

Yok edicisi.

```cpp
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıfı tarafından ayrılan kaynakları serbest bırakır ve [CAtlFileMappingBase:: eşlemesini Kaldır](#unmap) yöntemini çağırır.

## <a name="catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>CAtlFileMappingBase:: CopyFrom

Dosya eşleme nesnesinden kopyalamak için bu yöntemi çağırın.

```cpp
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>Parametreler

*cumg*<br/>
Kopyalanacak özgün dosya eşleme nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="catlfilemappingbasegetdata"></a><a name="getdata"></a>CAtlFileMappingBase:: GetData

Bir dosya eşleme nesnesinden verileri almak için bu yöntemi çağırın.

```cpp
void* GetData() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Veriye bir işaretçi döndürür.

## <a name="catlfilemappingbasegethandle"></a><a name="gethandle"></a>CAtlFileMappingBase:: GetHandle

Dosya eşleme nesnesine bir tanıtıcı döndürmek için bu yöntemi çağırın.

```cpp
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya eşleme nesnesine bir tanıtıcı döndürür.

## <a name="catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>CAtlFileMappingBase:: GetMappingSize

Bir dosya eşleme nesnesinden eşleme boyutunu almak için bu yöntemi çağırın.

```cpp
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme boyutunu döndürür.

### <a name="example"></a>Örnek

[CAtlFileMappingBase:: CAtlFileMappingBase](#catlfilemappingbase)örneğine bakın.

## <a name="catlfilemappingbasemapfile"></a><a name="mapfile"></a>CAtlFileMappingBase:: MapFile

Belirtilen dosya için bir dosya eşleme nesnesi açmak veya oluşturmak için bu yöntemi çağırın.

```cpp
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>Parametreler

*hFile*<br/>
Eşleme nesnesi oluşturulacak dosyanın tanıtıcısı. *hfile* geçerli olmalıdır ve INVALID_HANDLE_VALUE olarak ayarlanamaz.

*nMappingSize*<br/>
Eşleme boyutu. 0 ise, dosya eşleme nesnesinin en büyük boyutu *hfile* tarafından tanımlanan dosyanın geçerli boyutuna eşittir.

*nKonum*<br/>
Eşlemenin başlayacağı dosya konumu. Fark değeri, sistemin bellek ayırma ayrıntı düzeyinin katı olmalıdır.

*dwMappingProtection*<br/>
Dosya eşlendiğinde dosya görünümü için istenen koruma. Windows SDK bkz. [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) Içinde *flprotect* .

*dwViewDesiredAccess*<br/>
Dosya görünümüne erişimin türünü ve bu nedenle dosya tarafından eşlenen sayfaların korumasını belirtir. Windows SDK [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) Içindeki *dwDesiredAccess* öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bir dosya eşleme nesnesi oluşturulduktan sonra dosyanın boyutu dosya eşleme nesnesinin boyutunu aşmamalıdır; varsa, dosyanın içeriğinin hepsi paylaşım için kullanılabilir olmayacaktır. Daha fazla ayrıntı için Windows SDK [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) ve [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) bölümüne bakın.

### <a name="example"></a>Örnek

[CAtlFileMappingBase:: CAtlFileMappingBase](#catlfilemappingbase)örneğine bakın.

## <a name="catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>CAtlFileMappingBase:: MapSharedMem

Tüm işlemlere tam erişime izin veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.

```cpp
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Parametreler

*nMappingSize*<br/>
Eşleme boyutu. 0 ise, dosya eşleme nesnesinin en büyük boyutu, *szName*tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşittir.

*szName*<br/>
Eşleme nesnesinin adı.

*Pbalreadyvardı*<br/>
Eşleme nesnesi zaten mevcutsa, TRUE olarak ayarlanmış bir BOOL değeri gösterir.

*lpsa*<br/>
Döndürülen Tanıtıcının alt süreçler `SECURITY_ATTRIBUTES` tarafından devralınıp alınmayacağını belirleyen bir yapıya yönelik işaretçi. Windows SDK [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) Içindeki *lpattributes* bölümüne bakın.

*dwMappingProtection*<br/>
Dosya eşlendiğinde dosya görünümü için istenen koruma. Windows SDK 'da *Flprotect* `CreateFileMapping` bölümüne bakın.

*dwViewDesiredAccess*<br/>
Dosya görünümüne erişimin türünü ve bu nedenle dosya tarafından eşlenen sayfaların korumasını belirtir. Windows SDK [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) Içindeki *dwDesiredAccess* öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`MapShareMem`[CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga)tarafından oluşturulan mevcut bir dosya eşleme nesnesinin süreçler arasında paylaşılmasını sağlar.

## <a name="catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>CAtlFileMappingBase:: OpenMapping

Belirtilen dosya için adlandırılmış bir dosya eşleme nesnesi açmak için bu yöntemi çağırın.

```cpp
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Parametreler

*szName*<br/>
Eşleme nesnesinin adı. Bu ada sahip bir dosya eşleme nesnesine yönelik açık bir tanıtıcı varsa ve eşleme nesnesindeki güvenlik tanımlayıcısı *dwViewDesiredAccess* parametresiyle çakışıyorsa, açma işlemi başarılı olur.

*nMappingSize*<br/>
Eşleme boyutu. 0 ise, dosya eşleme nesnesinin en büyük boyutu, *szName*tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşittir.

*nKonum*<br/>
Eşlemenin başlayacağı dosya konumu. Fark değeri, sistemin bellek ayırma ayrıntı düzeyinin katı olmalıdır.

*dwViewDesiredAccess*<br/>
Dosya görünümüne erişimin türünü ve bu nedenle dosya tarafından eşlenen sayfaların korumasını belirtir. Windows SDK [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) Içindeki *dwDesiredAccess* öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, giriş parametreleri geçersiz olduğunda bir onaylama hatası oluşur.

## <a name="catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>CAtlFileMappingBase:: operator =

Geçerli dosya eşleme nesnesini başka bir dosya eşleme nesnesi olarak ayarlar.

```cpp
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>Parametreler

*cumg*<br/>
Geçerli dosya eşleme nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru döndürür.

## <a name="catlfilemappingbaseunmap"></a><a name="unmap"></a>CAtlFileMappingBase:: eşlemesini Kaldır

Dosya eşleme nesnesinin eşlemesini kaldırmak için bu yöntemi çağırın.

```cpp
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla ayrıntı için Windows SDK [UnmapViewOfFile dosyasına](/windows/win32/api/memoryapi/nf-memoryapi-unmapviewoffile) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlFileMapping Sınıfı](../../atl/reference/catlfilemapping-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
