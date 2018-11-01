---
title: Derleyici Seçenekleri makroları
ms.date: 11/04/2016
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
ms.openlocfilehash: d0da6ebcb178735fc25c656241fe23497d941ab6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631159"
---
# <a name="compiler-options-macros"></a>Derleyici Seçenekleri makroları

Bu makrolar özgü derleyici özelliklerini denetleyin.

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|ATL önceki sürümlerinden dönüştürülmüş projelerinde hatalar sağlayan bir simge|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Bir veya daha fazla nesnelerinizi iş parçacığı grubu kullanıyorsanız tanımlayın.|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Bilmesini sağlar `CString` oluşturucuları açık, yanlışlıkla dönüştürmenin engelliyor.|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Bir üye işlevine bir işaretçi başlatmak için standart olmayan bir sözdizimi kullanıldığında C4867 derleyici hatası oluşturur C++ Standart uyumlu sözdizimi kullanmak için bu makroyu tanımlar.|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Bir veya daha fazla nesnelerinizi ücretsiz veya nötr iş parçacığı kullanırsanız tanımlayın.|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Projeyi gösteren bir simge Both, boş veya nötr olarak işaretlenen nesneleri olacaktır. Makro [_ATL_FREE_THREADED](#_atl_free_threaded) bunun yerine kullanılmalıdır.|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|ATL olarak ad alanı varsayılan kullanımını engelleyen bir sembol|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM ilgili kod projenizi ile derlenmiş engelleyen bir simge.|
|[ATL_NO_VTABLE](#atl_no_vtable)|Vtable işaretçisi sınıfın oluşturucusu ve yıkıcısı başlatılmakta engelleyen bir simge.|
|[ATL_NOINLINE](#atl_noinline)|Bir işlev gösteren bir simge satır içine alınmış olmamalıdır.|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Tek iş parçacıklı model nesnelerinizi tüm kullandıysanız tanımlayın.|

##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS

ATL önceki sürümlerinden dönüştürülmüş projelerinde hatalar sağlayan bir simge

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>Açıklamalar

Visual C++ .NET 2002 önce ATL çok sayıda uyarı devre dışı ve bunları böylece bunlar hiçbir zaman kullanıcı kodunda hatırlarsınız devre dışı kaldı. Özellikle:

- C4127 koşullu ifade sabit

- C4786 'identifier': tanımlayıcı hata ayıklama bilgilerinde 'number' karakter olarak kesildi

- C4201 standart olmayan uzantı kullanıldı: Adsız yapı/birleşim

- C4103 'filename': #pragma paketini hizalamasını değiştirmek için kullanılır

- C4291 'bildirim': bulunamadı; eşleşen hiçbir delete işleci başlatma bir özel durum oluşturursa bellek serbest bırakılmaz

- C4268 'identifier': derleyicinin ürettiği varsayılan oluşturucuyla başlatılan 'const' statik/genel verileri nesneyi sıfırlarla dolduruyor

- Erişilemeyen kod C4702

Önceki sürümlerden dönüştürülen projelerinde, bu uyarılar hala kitaplıkları üstbilgileri tarafından devre dışı bırakıldı.

Aşağıdaki satırı stdafx.h dosyasına kitaplıkları üst bilgiler dahil olmak üzere önce ekleyerek, bu davranış değiştirilebilir.

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

Bu `#define` eklenir, böylece bunlar genel olarak devre dışı bırakılmaz (veya kullanıcı tarafından açıkça bunları etkinleştirmek için ayrı uyarılar devre dışı bırakıldığında) bu uyarıları durumunu korumak dikkatli ATL üstbilgilerine.

Yeni projeler sahip bu `#define` stdafx.h içinde varsayılan olarak ayarlayın.

##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED

Bir veya daha fazla nesnelerinizi iş parçacığı grubu kullanıyorsanız tanımlayın.

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>Açıklamalar

İş parçacığı grubu belirtir. Bkz [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) iş parçacığı için diğer seçenekler ve [ATL Basit Nesne Sihirbazı, seçenekleri](../../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller bir ATL nesnesi için kullanılabilir.

##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS

Bilmesini sağlar `CString` oluşturucuları açık, yanlışlıkla dönüştürmenin engelliyor.

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>Açıklamalar

Bu tanımlandığında, tek bir parametre tüm CString oluşturucuları giriş bağımsız değişkenlerinin örtülü dönüştürmeler engeller explicit anahtar sözcüğü ile derlenir. _UNICODE tanımlandığında, kullanım çalışırsanız, örneğin, yani char * dizesini, CString oluşturucu bağımsız değişkeni olarak bir derleyici hatasına neden olur. Bu makro, dar ve geniş dize türleri arasında örtük dönüştürme önlemek için gereken durumlarda kullanın.

_T makrosu tüm Oluşturucu dize bağımsız değişkenleri kullanarak _ATL_CSTRING_EXPLICIT_CONSTRUCTORS tanımlayın ve _UNICODE tanımlı olup olmadığı bağımsız olarak, derleme hatalarından kaçınmak.

##  <a name="_atl_enable_ptm_warning"></a>  _ATL_ENABLE_PTM_WARNING

Üye işaretçisi işlevlerine ANSI C++ standard uyumlu söz dizimi kullanılmasını zorlamak için bu makroyu tanımlar. Bu makroyu kullanarak, bir üye işlevine bir işaretçi başlatmak için standart olmayan söz dizimi kullanıldığında oluşturulacak C4867 derleyici hatasına neden olur.

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>Açıklamalar

ATL ve MFC kitaplıkları, Visual C++ derleyicisinin geliştirilmiş standart C++ uyumluluk eşleşecek şekilde değiştirildi. ANSI C++ standardına göre söz dizimi bir sınıf üyesi işlevi için bir işaretçi olmalıdır `&CMyClass::MyFunc`.

Zaman [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) tanımlanmamış böylece önceki sürümlerinde oluşturulan kod, önceki gibi oluşturmaya devam edebilirsiniz (varsayılan durumda) ATL/MFC C4867 hata makrosu Maps (özellikle ileti eşlemeleri) devre dışı bırakır. Tanımlarsanız **_ATL_ENABLE_PTM_WARNING**, kodunuzu C++ standardı ile uyumlu olmalıdır.

C++ Standart uyumlu sözdizimi için mevcut kodu Taşı gerekmez ancak standart form, kullanım dışıdır. Örneğin, aşağıdaki:

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

Şekilde değiştirilmelidir:

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

'&' Karakteri eklemek için eşleme makroları, onu yeniden kodunuzda eklemeyin olduğunu unutmayın.

##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED

Bir veya daha fazla nesnelerinizi ücretsiz veya nötr iş parçacığı kullanırsanız tanımlayın.

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>Açıklamalar

Serbest iş parçacığı oluşturmayı belirtir. Ücretsiz iş parçacığı için bir çoklu iş parçacığı apartman modeli eşdeğerdir. Bkz [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) iş parçacığı için diğer seçenekler ve [ATL Basit Nesne Sihirbazı, seçenekleri](../../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller bir ATL nesnesi için kullanılabilir.

##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED

Projeyi gösteren bir simge Both, boş veya nötr olarak işaretlenen nesneleri olacaktır.

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>Açıklamalar

Bu simge tanımlanmazsa, ATL genel veri erişim doğru eşitleyecek kodda çeker. Yeni kod eşdeğer makrosu kullanması gereken [_ATL_FREE_THREADED](#_atl_free_threaded) yerine.

##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE

ATL olarak ad alanı varsayılan kullanımını engelleyen bir sembol

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>Açıklamalar

Bu simge tanımlanmazsa, atlbase.h dahil olmak üzere gerçekleştirecek **using namespace ATL** varsayılan olarak, hangi açabilir adlandırma çakışmaları. Bunu önlemek için bu simge tanımlayın.

##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT

COM ilgili kod projenizi ile derlenmiş engelleyen bir simge.

```
_ATL_NO_COM_SUPPORT
```

##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE

Vtable işaretçisi sınıfın oluşturucusu ve yıkıcısı başlatılmakta engelleyen bir simge.

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>Açıklamalar

Vtable işaretçisi sınıfın oluşturucusu ve yıkıcısı başlatılmakta verilmemişse, bağlayıcı vtable ve tüm işaret ettiği işlevleri çıkarabilirsiniz. Genişletir **__declspec(novtable)**.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

##  <a name="atl_noinline"></a>  ATL_NOINLINE

Bir işlev gösteren bir simge satır içine alınmış olmamalıdır.

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>Parametreler

*myFunction*<br/>
İşlev satır içine alınmış olmamalıdır.

### <a name="remarks"></a>Açıklamalar

Bu simge, böylece bir üstbilgi dosyasına yerleştirilebilir, satır içi olarak bildirilmelidir olsa bile bir işlev derleyici tarafından satır içine almaz emin olmak istiyorsanız kullanın. Genişletir **__declspec(noinline)**.

##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED

Tek iş parçacıklı model nesnelerinizi tüm kullandıysanız tanımlayın

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>Açıklamalar

Nesne her zaman birincil COM iş parçacığında çalışır belirtir. Bkz [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) iş parçacığı için diğer seçenekler ve [ATL Basit Nesne Sihirbazı, seçenekleri](../../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller bir ATL nesnesi için kullanılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
