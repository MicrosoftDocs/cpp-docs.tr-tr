---
title: Derleyici Seçenekleri Makroları
ms.date: 08/19/2019
f1_keywords:
- _ATL_ALL_WARNINGS
- _ATL_APARTMENT_THREADED
- '_ATL_CSTRING_EXPLICIT_CONSTRUCTORS '
- _ATL_ENABLE_PTM_WARNING
- _ATL_FREE_THREADED
- _ATL_MULTI_THREADED
- _ATL_NO_AUTOMATIC_NAMESPACE
- _ATL_NO_COM_SUPPORT
- ATL_NO_VTABLE
- ATL_NOINLINE
- _ATL_SINGLE_THREADED
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
ms.openlocfilehash: 702324c3300ff23bb60113529a681e3b8fa99354
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331617"
---
# <a name="compiler-options-macros"></a>Derleyici Seçenekleri Makroları

Bu makrolar belirli derleyici özelliklerini denetler.

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|ATL'nin önceki sürümlerinden dönüştürülen projelerde hata yapılmasını sağlayan bir simge.|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Nesnelerinizden birinin veya daha fazlasının daire iş parçacığı kullanıp kullanmayın tanımlayın.|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Bazı `CString` yapıcıları açık hale getirir ve istenmeyen dönüşümleri önler.|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Bir üye işlev için işaretçi başlatmaiçin standart olmayan bir sözdizimi kullanıldığında C4867 derleyicisi hatasını oluşturan C++ standart uyumlu sözdizimini kullanmak için bu makroyu tanımlayın.|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Nesnelerinizden birinin veya daha fazlasının boş veya nötr iş parçacığı kullanıp kullanmayın.|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Projeyi gösteren bir sembol, Hem Serbest, hem de Nötr olarak işaretlenmiş nesnelere sahip olacaktır. Makro [_ATL_FREE_THREADED](#_atl_free_threaded) yerine kullanılmalıdır.|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Ad alanının Varsayılan Olarak ATL olarak kullanılmasını engelleyen bir simge.|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM ile ilgili kodun projenizle derlenmesine engel olan bir simge.|
|[ATL_NO_VTABLE](#atl_no_vtable)|Vtable işaretçisinin sınıfın oluşturucuve yıkıcısında başlatılmasını engelleyen bir simge.|
|[ATL_NOINLINE](#atl_noinline)|Bir işlevi gösteren bir sembol çizgili olmamalıdır.|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Tüm nesnelerinizin tek iş parçacığı modelini kullanıp kullanmayın tanımlayın.|

## <a name="_atl_all_warnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS

ATL'nin önceki sürümlerinden dönüştürülen projelerde hata yapılmasını sağlayan bir simge.

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>Açıklamalar

Visual C++ .NET 2002'den önce ATL birçok uyarıyı devre dışı bıraktı ve kullanıcı kodunda hiç gelmemesi için devre dışı bıraktı. Daha ayrıntılı şekilde belirtmek gerekirse:

- C4127 koşullu ifade sabittir

- C4786 'tanımlayıcı' : tanımlayıcı hata ayıklama bilgi 'sayı' karakterleri kesildi

- C4201 standart dışı uzantısı kullanılır : isimsiz yapı/birlik

- C4103 'filename' : hizalama değiştirmek için #pragma paketi kullanılır

- C4291 'bildirimi' : eşleşen operatör silme bulunamadı; başlatma bir özel durum atarsa bellek serbest bırakılmaz

- C4268 'tanımlayıcı' : Derleyici tarafından oluşturulan varsayılan yapı ile başharfe basılan 'const' statik/global veri nesneyi sıfırlarla doldurur

- C4702 erişilemez kod

Önceki sürümlerden dönüştürülen projelerde, bu uyarılar yine de kitaplık üstbilgitarafından devre dışı bırakılır.

Kitaplık başlıkları eklemeden önce *pch.h* *(Visual* Studio 2017 ve önceki) dosyasına aşağıdaki satırı ekleyerek bu davranış değiştirilebilir.

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

Bu `#define` eklenirse, ATL üstbilgisi, genel olarak devre dışı bırakılmaması için bu uyarıların durumunu korumaya dikkat eder (veya kullanıcı tek tek uyarıları etkinleştirmek için açıkça devre dışı kılmışsa).

Yeni projeler `#define` varsayılan olarak *pch.h* (Visual Studio 2017 ve önceki*stdafx.h)* bu set var.

## <a name="_atl_apartment_threaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED

Nesnelerinizden birinin veya daha fazlasının daire iş parçacığı kullanıp kullanmayın tanımlayın.

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>Açıklamalar

Daire iş parçacığı belirtir. Bkz. Diğer iş parçacığı seçenekleri için [Projenin İş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) ve ATL nesnesi için kullanılabilen iş parçacığı modellerinin açıklaması için [ATL Basit Nesne Sihirbazı.](../../atl/reference/options-atl-simple-object-wizard.md)

## <a name="_atl_cstring_explicit_constructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS

Bazı `CString` yapıcıları açık hale getirir ve istenmeyen dönüşümleri önler.

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu tanımlandığında, tek bir parametre alan tüm CString oluşturucuları, giriş bağımsız değişkenlerinin örtülü dönüşümlerini engelleyen açık anahtar kelimeyle derlenir. Bu, örneğin, _UNICODE tanımlandığında, bir char* dizesini CString oluşturucu bağımsız değişkeni olarak kullanmaya çalışırsanız, derleyici hatasının neden olacağı anlamına gelir. Dar ve geniş dize türleri arasında örtük dönüşümleri önlemeniz gereken durumlarda bu makroyu kullanın.

Tüm oluşturucu dize bağımsız değişkenlerinde _T makroyu kullanarak, _ATL_CSTRING_EXPLICIT_CONSTRUCTORS tanımlayabilir ve _UNICODE tanımlanıp tanımlanmadığına bakılmaksızın hataları derlemekten kaçınabilirsiniz.

## <a name="_atl_enable_ptm_warning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING

Bu makroyu, işaretçi için ansi C++ standart uyumlu sözdizimini üye işlevlere zorlamak için tanımlayın. Bu makroyu kullanmak, bir üye işlev için işaretçiyi başlatmak için standart olmayan sözdizimi kullanıldığında C4867 derleyicisi hatasının oluşturulmasına neden olur.

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>Açıklamalar

ATL ve MFC kitaplıkları, Microsoft C++ derleyicisinin geliştirilmiş standart C++ uyumluluğuyla eşleşecek şekilde değiştirildi. ANSI C++ standardına göre, bir sınıf üye işleviiçin bir `&CMyClass::MyFunc`işaretçinin sözdizimi olmalıdır.

[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) tanımlanmadığında (varsayılan durum), ATL/MFC makro eşlemlerde (özellikle ileti haritaları) C4867 hatasını devre dışı kakTırıyor, böylece önceki sürümlerde oluşturulan kod eskisi gibi oluşturmaya devam edebilir. **_ATL_ENABLE_PTM_WARNING**tanımlarsanız, kodunuz C++ standart uyumlu olmalıdır.

Ancak, standart olmayan form amortismana uğradı. Varolan kodu C++ standart uyumlu sözdizimine taşımanız gerekir. Örneğin, aşağıdaki kod:

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

Şöyle değiştirilmelidir:

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

Harita makroları için ampersand '&' karakterini ekleyin. Koduna karakteri tekrar eklememelisin.

## <a name="_atl_free_threaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED

Nesnelerinizden birinin veya daha fazlasının boş veya nötr iş parçacığı kullanıp kullanmayın.

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>Açıklamalar

Serbest iş parçacığı belirtir. Ücretsiz iş parçacığı çok iş parçacığı daire modeline eşdeğerdir. Bkz. Diğer iş parçacığı seçenekleri için [Projenin İş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) ve ATL nesnesi için kullanılabilen iş parçacığı modellerinin açıklaması için [ATL Basit Nesne Sihirbazı.](../../atl/reference/options-atl-simple-object-wizard.md)

## <a name="_atl_multi_threaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED

Projeyi gösteren bir sembol, Hem Serbest, hem de Nötr olarak işaretlenmiş nesnelere sahip olacaktır.

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>Açıklamalar

Bu sembol tanımlanırsa, ATL küresel verilere erişimi doğru şekilde eşitleyecek kod çeker. Yeni kod yerine eşdeğer makro [_ATL_FREE_THREADED](#_atl_free_threaded) kullanmalıdır.

## <a name="_atl_no_automatic_namespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE

Ad alanının Varsayılan Olarak ATL olarak kullanılmasını engelleyen bir simge.

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>Açıklamalar

Bu sembol tanımlanmamışsa, atlbase.h dahil olmak üzere varsayılan olarak **ad alanı ATL kullanarak** gerçekleştirecektir, bu da ad çakışmalarına neden olabilir. Bunu önlemek için bu sembolü tanımlayın.

## <a name="_atl_no_com_support"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT

COM ile ilgili kodun projenizle derlenmesine engel olan bir simge.

```
_ATL_NO_COM_SUPPORT
```

## <a name="atl_no_vtable"></a><a name="atl_no_vtable"></a>ATL_NO_VTABLE

Vtable işaretçisinin sınıfın oluşturucuve yıkıcısında başlatılmasını engelleyen bir simge.

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>Açıklamalar

Vtable işaretçisinin sınıfın oluşturucuve yıkıcısında başlatılması engellenirse, bağlayıcı vtable'ı ve işaret ettiği tüm işlevleri ortadan kaldırabilir. **__declspec(novtable)** genişletir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

## <a name="atl_noinline"></a><a name="atl_noinline"></a>ATL_NOINLINE

Bir işlevi gösteren bir sembol çizgili olmamalıdır.

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>Parametreler

*Myfunction*<br/>
Çizgili olmamalıdır işlevi.

### <a name="remarks"></a>Açıklamalar

Bir işlevin derleyici tarafından sıralanmadığından emin olmak istiyorsanız, üstbilgi dosyasına yerleştirilebilmesi için satır adı olarak bildirilmesi gerekse bile bu sembolü kullanın. **__declspec (noinline)** genişletir.

## <a name="_atl_single_threaded"></a><a name="_atl_single_threaded"></a>_ATL_SINGLE_THREADED

Tüm nesnelerinizin tek iş parçacığı modelini kullanıp kullanmama

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>Açıklamalar

Nesnenin her zaman birincil COM iş parçacığında çalıştığını belirtir. Bkz. Diğer iş parçacığı seçenekleri için [Projenin İş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) ve ATL nesnesi için kullanılabilen iş parçacığı modellerinin açıklaması için [ATL Basit Nesne Sihirbazı.](../../atl/reference/options-atl-simple-object-wizard.md)

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
