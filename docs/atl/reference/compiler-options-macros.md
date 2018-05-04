---
title: Derleyici Seçenekleri makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e84c92e8bbf65ff3b8b54111bcce2306628edb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-options-macros"></a>Makro derleyici seçenekleri
Bu makroları belirli derleyicisi özelliklerini denetler.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|ATL önceki sürümlerinden dönüştürülen projelerinde hataları sağlayan bir simge|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Bir veya daha fazla nesnelerinizi Apartman iş parçacığı oluşturma kullanırsanız tanımlayın.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Belirli yapar `CString` oluşturucular açık istenmeyen dönüştürmenin engelliyor.|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Üye işlevi için bir işaretçi başlatmak için standart olmayan bir sözdizimi kullanıldığında C4867 derleyici hatası oluşturur C++ Standart uyumlu sözdizimi kullanmak için bu makrosu tanımlayın.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Bir veya daha fazla nesnelerinizi boş veya nötr iş parçacığı oluşturma kullanırsanız tanımlayın.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Proje gösteren bir simge Both, boş veya bağımsız olarak işaretlenen nesneleri sahip olur. Makro [_ATL_FREE_THREADED](#_atl_free_threaded) bunun yerine kullanılmalıdır.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|ATL olarak ad alanı varsayılan kullanımını önleyen bir simge|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|COM ile ilgili kod projenizle derlenmiş engelleyen bir simge.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Sınıfının oluşturucusu ve yıkıcı başlatılmış vtable işaretçi engeller bir simge.|  
|[ATL_NOINLINE](#atl_noinline)|Bir işlev gösteren bir simge içermesinden olmamalıdır.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Tüm nesnelerinin tek iş parçacığı modelini kullandıysanız tanımlayın.|  
  
##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS  
 ATL önceki sürümlerinden dönüştürülen projelerinde hataları sağlayan bir simge  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Açıklamalar  
 Visual C++ .NET 2002 önce ATL çok sayıda uyarı devre dışı ve bunları böylece bunlar hiçbir zaman içinde kullanıcı kodu gösterdi devre dışı bırakıldı. Özellikle:  
  
-   C4127 koşullu ifade sabittir  
  
-   C4786 'tanımlayıcısı': hata ayıklama bilgileri 'numara' karakter tanımlayıcı kesildi  
  
-   Kullanılan C4201 standart olmayan uzantısı: Adsız struct/birleşim  
  
-   C4103 'filename': #pragma paketi hizalama değiştirmek için kullanılır  
  
-   C4291 'bildirimi': bulundu; hiçbir eşleşen delete işleci başlatma bir özel durum oluşturursa bellek serbest bırakılmaz  
  
-   C4268 'tanımlayıcısı': oluşturulan derleyici varsayılan kurucu ile başlatılmış 'const' statik/genel veri sıfırlarla nesnesini doldurur  
  
-   C4702 ulaşılamaz kod  
  
 Önceki sürümlerden dönüştürülen projelerde, bu uyarılar hala kitaplıkları üstbilgileri tarafından devre dışı bırakılır.  
  
 Aşağıdaki satırı stdafx.h dosyasına kitaplıkları üstbilgileri eklemeden önce ekleyerek, bu davranış değiştirilebilir.  
  
 [!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 Bu `#define` eklenir, böylece bunlar genel devre dışı olmadığını (veya kullanıcı açıkça bunları etkinleştirmemeyi bireysel uyarıları devre dışı bırakır) Bu uyarılar durumunu korumak dikkatli ATL üstbilgileri.  
  
 Yeni projeler sahip bu `#define` Stdafx.h'de varsayılan olarak ayarlayın.  
  
##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED  
 Bir veya daha fazla nesnelerinizi Apartman iş parçacığı oluşturma kullanırsanız tanımlayın.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Açıklamalar  
 Apartman iş parçacığı oluşturma belirtir. Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) diğer için iş parçacığı oluşturma seçenekleri ve [seçenekleri, ATL Basit Nesne Sihirbazı](../../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller ATL nesne için kullanılabilir.  
  
##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 Belirli yapar `CString` oluşturucular açık istenmeyen dönüştürmenin engelliyor.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tanımlandığında, tek bir parametre alan tüm CString oluşturucular giriş bağımsız değişkenleri örtük dönüşümler engeller explicit anahtar sözcüğü ile derlenir. _UNICODE tanımlandığında, kullanım çalışırsanız, örneğin, yani char * dizesini, CString oluşturucu bağımsız değişkeni olarak bir derleyici hatasına neden olur. Bu makrosu burada dar ve geniş dize türleri arasında örtük dönüşümler önlemek için gereken durumlarda kullanın.  
  
 Tüm Oluşturucusu dize bağımsız değişkenleri _T makrosu kullanarak _UNICODE olup tanımlanan bakılmaksızın derleme hatalarını önlemek ve _ATL_CSTRING_EXPLICIT_CONSTRUCTORS tanımlayın.  
  
##  <a name="_atl_enable_ptm_warning"></a>  _ATL_ENABLE_PTM_WARNING  
 Üye işlevleri işaretçisine ANSI C++ Standart uyumlu sözdizimi kullanılmasını zorlamak için bu makrosu tanımlayın. Bu makrosu kullanarak C4867 derleyici hatası üye işlevi için bir işaretçi başlatmak için standart olmayan sözdizimi kullanıldığında oluşturulmasına neden olur.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL ve MFC kitaplıkları, Visual C++ derleyicinin geliştirilmiş standart C++ uyumluluk eşleşecek şekilde değiştirildi. ANSI C++ Standart göre sınıf üye işlevi için bir işaretçi sözdizimi olmalıdır `&CMyClass::MyFunc`.  
  
 Zaman [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) tanımlı değil olarak önce oluşturmak önceki sürümlerde oluşturulmuş kodu devam edebilmesi için (varsayılan durumda) ATL/MFC (özellikle ileti eşlemeleri) makrosu Maps C4867 hata devre dışı bırakır. Tanımlarsanız **_ATL_ENABLE_PTM_WARNING**, kodunuzu C++ Standart uyumlu olmalıdır.  
  
 C++ Standart uyumlu sözdizimi için var olan kodu taşımanız gerekir böylece ancak, standart olmayan form, kullanım dışı bırakıldı. Örneğin, aşağıdaki:  
  
 [!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 Değiştirilmelidir:  
  
 [!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 '&' Karakteri eklemek eşleme makroları için onu yeniden kodunuzda eklemeyin olduğunu unutmayın.  
  
##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED  
 Bir veya daha fazla nesnelerinizi boş veya nötr iş parçacığı oluşturma kullanırsanız tanımlayın.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Açıklamalar  
 Boş iş parçacığı oluşturma belirtir. Boş iş parçacığı oluşturma için çoklu iş parçacığı apartman modeli eşdeğerdir. Bkz: [projenin iş parçacıklı Model belirtme](../../atl/specifying-the-threading-model-for-a-project-atl.md) diğer için iş parçacığı oluşturma seçenekleri ve [seçenekleri, ATL Basit Nesne Sihirbazı](../../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller ATL nesne için kullanılabilir.  
  
##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED  
 Proje gösteren bir simge Both, boş veya bağımsız olarak işaretlenen nesneleri sahip olur.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu simgenin tanımlanmışsa ATL genel verilere erişimin doğru eşitler kodda çeker. Yeni kod eşdeğer makrosu kullanması gereken [_ATL_FREE_THREADED](#_atl_free_threaded) yerine.  
  
##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE  
 ATL olarak ad alanı varsayılan kullanımını önleyen bir simge  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu simgeyi tanımlanmazsa atlbase.h dahil olmak üzere gerçekleştirecek **ad alanı ATL kullanılarak** varsayılan olarak, hangi açabilir adlandırma çakışmaları. Bunu önlemek için bu simgeyi tanımlayın.  
  
##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT  
 COM ile ilgili kod projenizle derlenmiş engelleyen bir simge.  
  
```
_ATL_NO_COM_SUPPORT```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 A symbol that prevents the vtable pointer from being initialized in the class's constructor and destructor.  
  
```
ATL_NO_VTABLE
```  
  
### Remarks  
 If the vtable pointer is prevented from being initialized in the class's constructor and destructor, the linker can eliminate the vtable and all of the functions to which it points. Expands to **__declspec(novtable)**.  
  
### Example  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 A symbol that indicates a function should not be inlined.  
  
```
    ATL_NOINLINE inline
    myfunction
 { ... }
```  
  
### Parameters  
 *myfunction*  
 The function that should not be inlined.  
  
### Remarks  
 Use this symbol if you want to ensure a function does not get inlined by the compiler, even though it must be declared as inline so that it can be placed in a header file. Expands to **__declspec(noinline)**.  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 Define if all of your objects use the single threading model  
  
```
_ATL_SINGLE_THREADED
```  
  
### Remarks  
 Specifies that the object always runs in the primary COM thread. See [Specifying the Project's Threading Model](../../atl/specifying-the-threading-model-for-a-project-atl.md) for other threading options, and [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) for a description of the threading models available for an ATL object.  
  
## See Also  
 [Macros](../../atl/reference/atl-macros.md)
