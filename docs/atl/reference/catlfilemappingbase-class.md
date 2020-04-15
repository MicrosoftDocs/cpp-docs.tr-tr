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
ms.openlocfilehash: ae790cf1248c78ff9aa70c0e586f86af6c8f3b9a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318948"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase Sınıfı

Bu sınıf, bellek eşlenen bir dosyayı temsil eder.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlFileMappingBase
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Oluşturucu.|
|[CAtlFileMappingBase::~CAtlFileMappingBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Dosya eşleme nesnesinden kopyalamak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::Veri Alın](#getdata)|Dosya eşleme nesnesinden veri almak için bu yöntemi arayın.|
|[CAtlFileMappingBase::GetHandle](#gethandle)|Dosya tanıtıcısını döndürmek için bu yöntemi arayın.|
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Dosya eşleme nesnesinden eşleme boyutunu almak için bu yöntemi arayın.|
|[CAtlFileMappingBase::MapFile](#mapfile)|Dosya eşleme nesnesi oluşturmak için bu yöntemi çağırın.|
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Tüm işlemlere tam erişime izin veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi arayın.|
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Dosya eşleme nesnesine bir tanıtıcı döndürmek için bu yöntemi çağırın.|
|[CAtlFileMappingBase::Haritayı kapatma](#unmap)|Dosya eşleme nesnesini açmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlFileMappingBase::operatör =](#operator_eq)|Geçerli dosya eşleme nesnesini başka bir dosya eşleme nesnesine ayarlar.|

## <a name="remarks"></a>Açıklamalar

Dosya eşleme, bir işlemin sanal adres alanının bir bölümüyle dosya içeriğinin ilişkilendirilmesidir. Bu sınıf, programların verilere kolayca erişebilen ve paylaşabilen dosya eşleme nesneleri oluşturmak için yöntemler sağlar.

Daha fazla bilgi için Windows SDK'daki [Dosya Eşleme'ye](/windows/win32/Memory/file-mapping) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlfile.h

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase

Oluşturucu.

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>Parametreler

*orig*<br/>
Yeni nesne oluşturmak için kopyalamak için özgün dosya eşleme nesnesi.

### <a name="remarks"></a>Açıklamalar

İsteğe bağlı olarak varolan bir nesneyi kullanarak yeni bir dosya eşleme nesnesi oluşturur. Belirli bir dosya için dosya eşleme nesnesini açmak veya oluşturmak için [CAtlFileMappingBase::MapFile'ı](#mapfile) aramak yine de gereklidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>CAtlFileMappingBase::~CAtlFileMappingBase

Yıkıcı.

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>Açıklamalar

Sınıf tarafından ayrılan tüm kaynakları serbest eder ve [CAtlFileMappingBase::Unmap](#unmap) yöntemini çağırır.

## <a name="catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>CAtlFileMappingBase::CopyFrom

Dosya eşleme nesnesinden kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>Parametreler

*orig*<br/>
Kopyalanması gereken özgün dosya eşleme nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="catlfilemappingbasegetdata"></a><a name="getdata"></a>CAtlFileMappingBase::Veri Alın

Dosya eşleme nesnesinden veri almak için bu yöntemi arayın.

```
void* GetData() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Verilere bir işaretçi döndürür.

## <a name="catlfilemappingbasegethandle"></a><a name="gethandle"></a>CAtlFileMappingBase::GetHandle

Dosya eşleme nesnesine bir tanıtıcı döndürmek için bu yöntemi çağırın.

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tanıtıcıyı dosya eşleme nesnesine döndürür.

## <a name="catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize

Dosya eşleme nesnesinden eşleme boyutunu almak için bu yöntemi arayın.

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme boyutunu döndürür.

### <a name="example"></a>Örnek

[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)için örneğe bakın.

## <a name="catlfilemappingbasemapfile"></a><a name="mapfile"></a>CAtlFileMappingBase::MapFile

Belirtilen dosya için bir dosya eşleme nesnesini açmak veya oluşturmak için bu yöntemi çağırın.

```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>Parametreler

*hFile*<br/>
Eşleme nesnesi oluşturmak için dosyaya işitin. *hFile* geçerli olmalıdır ve INVALID_HANDLE_VALUE olarak ayarlanamaz.

*nMappingSize*<br/>
Haritalama boyutu. 0 ise, dosya eşleme nesnesinin maksimum boyutu hFile tarafından tanımlanan dosyanın geçerli boyutuna *eşittir.*

*nOffset*<br/>
Eşlemenin başlayacağı dosya ofset. Ofset değeri, sistemin bellek ayırma parçalı lığının bir katı olmalıdır.

*dwMappingProtection*<br/>
Dosya eşlendiğinde dosya görünümü için istenen koruma. Windows SDK'da [CreateFileMapping'te](/windows/win32/api/winbase/nf-winbase-createfilemappinga) *flProtect'e* bakın.

*dwViewDesiredAccess*<br/>
Dosya görünümüne erişim türünü ve bu nedenle dosya tarafından eşlenen sayfaların korunmasını belirtir. Windows SDK'daki [MapViewOfFileEx'te](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) *dwDesiredAccess'e* bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bir dosya eşleme nesnesi oluşturulduktan sonra, dosyanın boyutu dosya eşleme nesnesinin boyutunu aşmamalıdır; varsa, dosyanın tüm içeriği paylaşılacak değildir. Daha fazla bilgi için Windows SDK'daki [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) ve [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) bölümüne bakın.

### <a name="example"></a>Örnek

[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)için örneğe bakın.

## <a name="catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem

Tüm işlemlere tam erişime izin veren bir dosya eşleme nesnesi oluşturmak için bu yöntemi arayın.

```
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
Haritalama boyutu. 0 ise, dosya eşleme nesnesinin maksimum boyutu *szName*tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşittir.

*Szname*<br/>
Eşleme nesnesinin adı.

*pbAlreadyExisted*<br/>
Eşleme nesnesi zaten varsa TRUE olarak ayarlanmış bir BOOL değerine işaret ediyor.

*lpsa*<br/>
Döndürülen tanıtıcının alt işlemler tarafından devralınıp alınamayacağını belirleyen bir `SECURITY_ATTRIBUTES` yapının işaretçisi. Windows SDK'da [CreateFileMapping'te](/windows/win32/api/winbase/nf-winbase-createfilemappinga) *lpAttributes'a* bakın.

*dwMappingProtection*<br/>
Dosya eşlendiğinde dosya görünümü için istenen koruma. Bkz. windows `CreateFileMapping` SDK'da *flProtect* içinde.

*dwViewDesiredAccess*<br/>
Dosya görünümüne erişim türünü ve bu nedenle dosya tarafından eşlenen sayfaların korunmasını belirtir. Windows SDK'daki [MapViewOfFileEx'te](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) *dwDesiredAccess'e* bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

`MapShareMem`[CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga)tarafından oluşturulan varolan bir dosya eşleme nesnesi, işlemler arasında paylaşılmasına izin verir.

## <a name="catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>CAtlFileMappingBase::OpenMapping

Belirtilen dosya için adlandırılmış bir dosya eşleme nesnesi açmak için bu yöntemi çağırın.

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Parametreler

*Szname*<br/>
Eşleme nesnesinin adı. Bu ada göre bir dosya eşleme nesnesine açık bir tutamaç varsa ve eşleme nesnesindeki güvenlik tanımlayıcısı *dwViewDesiredAccess* parametresi ile çakışmazsa, açık işlem başarılı olur.

*nMappingSize*<br/>
Haritalama boyutu. 0 ise, dosya eşleme nesnesinin maksimum boyutu *szName*tarafından tanımlanan dosya eşleme nesnesinin geçerli boyutuna eşittir.

*nOffset*<br/>
Eşlemenin başlayacağı dosya ofset. Ofset değeri, sistemin bellek ayırma parçalı lığının bir katı olmalıdır.

*dwViewDesiredAccess*<br/>
Dosya görünümüne erişim türünü ve bu nedenle dosya tarafından eşlenen sayfaların korunmasını belirtir. Windows SDK'daki [MapViewOfFileEx'te](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) *dwDesiredAccess'e* bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, giriş parametreleri geçersizse bir tasnif hatası oluşur.

## <a name="catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>CAtlFileMappingBase::operatör =

Geçerli dosya eşleme nesnesini başka bir dosya eşleme nesnesine ayarlar.

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>Parametreler

*orig*<br/>
Geçerli dosya eşleme nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru verir.

## <a name="catlfilemappingbaseunmap"></a><a name="unmap"></a>CAtlFileMappingBase::Haritayı kapatma

Dosya eşleme nesnesini açmak için bu yöntemi çağırın.

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'da [UnmapViewOfFile](/windows/win32/api/memoryapi/nf-memoryapi-unmapviewoffile) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlFileMapping Sınıfı](../../atl/reference/catlfilemapping-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
