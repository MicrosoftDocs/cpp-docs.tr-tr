---
title: Derleyici seçenekleri makroları
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
ms.openlocfilehash: d8c9538c9f3d889360c0527ba538e9e091df0755
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229967"
---
# <a name="compiler-options-macros"></a>Derleyici seçenekleri makroları

Bu makrolar belirli derleyici özelliklerini denetler.

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|ATL 'nin önceki sürümlerinden dönüştürülen projelerde hata veren bir sembol.|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Nesnelerinizin bir veya daha fazla apartman iş parçacığı kullanıp kullanmıyorsa tanımlayın.|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Belirli `CString` oluşturucuları açık hale getirir, istenmeden dönüştürmeleri önler.|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Bir üye işlevine bir işaretçi başlatmak için standart olmayan bir sözdizimi kullanıldığında, C4867 derleyici hatası oluşturan C++ standart uyumlu söz dizimini kullanmak için bu makroyu tanımlayın.|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Nesnelerinizin bir veya daha fazla serbest iş parçacığı kullanıp kullanmıyorsa tanımlayın.|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Projenin hem, serbest veya nötr olarak işaretlenen nesneleri olacağını gösteren bir simge. Bunun yerine makro [_ATL_FREE_THREADED](#_atl_free_threaded) kullanılmalıdır.|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Ad alanının ATL olarak varsayılan kullanımını önleyen bir simge.|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM ile ilgili kodun projenizle derlenmelerini engelleyen bir simge.|
|[ATL_NO_VTABLE](#atl_no_vtable)|Vtable işaretçisinin sınıfın oluşturucusunda ve yıkıcısında başlatılmasını engelleyen bir simge.|
|[ATL_NOINLINE](#atl_noinline)|Bir işlevin satır içine alınmayacak olması gerektiğini belirten bir simge.|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Tüm nesnelerinizin tek iş parçacığı modelini kullanıp kullan, tanımlayın.|

## <a name="_atl_all_warnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS

ATL 'nin önceki sürümlerinden dönüştürülen projelerde hata veren bir sembol.

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>Açıklamalar

Visual C++ .NET 2002 ' den önce, ATL çok sayıda uyarıyı devre dışı bırakmış ve Kullanıcı kodunda hiç gösterilmemesi için devre dışı bıraktı. Özellikle:

- C4127 koşullu ifade sabit

- C4786 ' identifier ': tanımlayıcı hata ayıklama bilgilerinde ' number ' karakter olarak kesildi

- C4201 standart olmayan uzantı kullanıldı: adsız struct/Union

- C4103 ' filename ': hizalamayı değiştirmek için #pragma paketi kullanıldı

- C4291 ' declaration ': eşleşen bir işleç silme bulunamadı; başlatma bir özel durum oluşturursa bellek boşaltılmaz

- C4268 ' Identifier ': derleyicinin ürettiği varsayılan oluşturucuyla başlatılan ' const ' statik/genel verileri nesneyi sıfırlarla doldurur

- C4702 ulaşılamıyor kodu

Önceki sürümlerden dönüştürülen projelerde, bu uyarılar kitaplık üstbilgileri tarafından hala devre dışı bırakılır.

Aşağıdaki satırı, kitaplık üstbilgilerini dahil etmeden önce *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) dosyasına ekleyerek bu davranış değiştirilebilir.

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

Bu `#define` eklenirse, ATL üstbilgileri, genel olarak devre dışı bırakılmaması için bu uyarıların durumunu korumak için dikkatli olur (veya kullanıcı açıkça uyarıları devre dışı bırakır, bunları etkinleştirmek için).

Yeni projeler bu, `#define` Varsayılan olarak *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) ' de ayarlanır.

## <a name="_atl_apartment_threaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED

Nesnelerinizin bir veya daha fazla apartman iş parçacığı kullanıp kullanmıyorsa tanımlayın.

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>Açıklamalar

Apartman iş parçacığı belirtir. Bir ATL nesnesi için kullanılabilir iş parçacığı modellerinin bir açıklaması için diğer iş parçacığı seçenekleri ve [Seçenekler, atl basit nesne Sihirbazı](../../atl/reference/options-atl-simple-object-wizard.md) Için [projenin Iş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) bölümüne bakın.

## <a name="_atl_cstring_explicit_constructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS

Belirli `CString` oluşturucuları açık hale getirir, istenmeden dönüştürmeleri önler.

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>Açıklamalar

Bu Oluşturucu tanımlandığında, tek bir parametre alan tüm CString oluşturucular açık anahtar sözcükle derlenir ve bu da giriş bağımsız değişkenlerinin örtük dönüştürmelerini önler. Bu, örneğin, _UNICODE tanımlandığında, bir CString Oluşturucu bağımsız değişkeni olarak bir Char * dizesi kullanmaya çalışırsanız, bir derleyici hatasının sonuçlanabileceğini gösterir. Dar ve geniş dize türleri arasında örtük dönüştürmeleri engellemeniz gereken durumlarda bu makroyu kullanın.

Tüm Oluşturucu dize bağımsız değişkenlerinde _T makrosunu kullanarak _ATL_CSTRING_EXPLICIT_CONSTRUCTORS tanımlayabilir ve _UNICODE tanımlanıp tanımlanmadığına bakılmaksızın derleme hatalarından kaçınabilirsiniz.

## <a name="_atl_enable_ptm_warning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING

Üye işlevlerine işaretçi için ANSI C++ standart uyumlu sözdizimi kullanımını zorlamak üzere bu makroyu tanımlayın. Bu makronun kullanılması, bir üye işlevine bir işaretçi başlatmak için standart olmayan bir sözdizimi kullanıldığında C4867 derleyici hatasının oluşturulmasına neden olur.

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>Açıklamalar

ATL ve MFC kitaplıkları, Microsoft C++ derleyicisinin geliştirilmiş standart C++ uyumluluğuyla eşleşecek şekilde değiştirilmiştir. ANSI C++ standardına göre, bir sınıf üye işlevine yönelik işaretçinin sözdizimi olmalıdır `&CMyClass::MyFunc` .

[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) tanımlı olmadığında (varsayılan durum), ATL/MFC, daha önceki sürümlerde oluşturulan kodun daha önce olduğu gibi derlenmeye devam edebilmesi için makro haritaları 'nda (özellikle ileti haritaları) C4867 hatasını devre dışı bırakır. **_ATL_ENABLE_PTM_WARNING**tanımlarsanız, kodunuz C++ standart uyumlu olmalıdır.

Ancak standart olmayan form kullanım dışı bırakılmıştır. Mevcut kodu C++ standart uyumlu sözdizimine taşımanız gerekir. Örneğin, aşağıdaki kod:

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

Şöyle değiştirilmelidir:

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

Harita makroları için ve ' & ' karakterini ekleyin. Kodunuzda karakteri tekrar eklememelisiniz.

## <a name="_atl_free_threaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED

Nesnelerinizin bir veya daha fazla serbest iş parçacığı kullanıp kullanmıyorsa tanımlayın.

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>Açıklamalar

Serbest iş parçacığı belirtir. Ücretsiz iş parçacığı, bir çoklu iş parçacığı grubu modeliyle eşdeğerdir. Bir ATL nesnesi için kullanılabilir iş parçacığı modellerinin bir açıklaması için diğer iş parçacığı seçenekleri ve [Seçenekler, atl basit nesne Sihirbazı](../../atl/reference/options-atl-simple-object-wizard.md) Için [projenin Iş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) bölümüne bakın.

## <a name="_atl_multi_threaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED

Projenin hem, serbest veya nötr olarak işaretlenen nesneleri olacağını gösteren bir simge.

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>Açıklamalar

Bu sembol tanımlanmışsa, ATL genel verilere erişimi doğru bir şekilde eşitleyecek kodu çeker. Yeni kod, bunun yerine eşdeğer makro [_ATL_FREE_THREADED](#_atl_free_threaded) kullanmalıdır.

## <a name="_atl_no_automatic_namespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE

Ad alanının ATL olarak varsayılan kullanımını önleyen bir simge.

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>Açıklamalar

Bu simge tanımlı değilse, atlbase. h dahil olmak üzere varsayılan olarak **ad alanı ATL kullanılarak** yapılır, bu da adlandırma çakışmalarına neden olabilir. Bunu engellemek için bu simgeyi tanımlayın.

## <a name="_atl_no_com_support"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT

COM ile ilgili kodun projenizle derlenmelerini engelleyen bir simge.

```
_ATL_NO_COM_SUPPORT
```

## <a name="atl_no_vtable"></a><a name="atl_no_vtable"></a>ATL_NO_VTABLE

Vtable işaretçisinin sınıfın oluşturucusunda ve yıkıcısında başlatılmasını engelleyen bir simge.

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>Açıklamalar

Vtable işaretçisinin, sınıfın oluşturucusunda ve yıkıcısında başlatılmasının engellenmemesi durumunda bağlayıcı, vtable 'ı ve işaret ettiği tüm işlevleri ortadan kaldırabilir. Öğesini olarak genişletir **`__declspec(novtable)`** .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

## <a name="atl_noinline"></a><a name="atl_noinline"></a>ATL_NOINLINE

Bir işlevin satır içine alınmayacak olduğunu gösteren bir simge.

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>Parametreler

*MyFunction*<br/>
Satır içine alınmayacak olması gereken işlev.

### <a name="remarks"></a>Açıklamalar

Bir işlevin, bir üst bilgi dosyasına yerleştirilebilecek şekilde, satır içi olarak bildirilmesini gerektirse de, bu simgeyi kullanın. Öğesini olarak genişletir **`__declspec(noinline)`** .

## <a name="_atl_single_threaded"></a><a name="_atl_single_threaded"></a>_ATL_SINGLE_THREADED

Tüm nesnelerinizin tek iş parçacığı modelini kullanıp kullanmıyorsa tanımlayın

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>Açıklamalar

Nesnenin her zaman birincil COM iş parçacığında çalışacağını belirtir. Bir ATL nesnesi için kullanılabilir iş parçacığı modellerinin bir açıklaması için diğer iş parçacığı seçenekleri ve [Seçenekler, atl basit nesne Sihirbazı](../../atl/reference/options-atl-simple-object-wizard.md) Için [projenin Iş parçacığı modelini belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
