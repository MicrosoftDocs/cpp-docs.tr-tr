---
title: "Çalışma zamanı nesne modeli Hizmetleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 986657681dabf1136b072f65b2df76b63f216504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="run-time-object-model-services"></a>Çalışma Süresi Nesne Modeli Hizmetleri
Sınıfları [CObject](../../mfc/reference/cobject-class.md) ve [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) erişim çalışma zamanı sınıf bilgileri, seri hale getirme ve dinamik Nesne oluşturma dahil olmak üzere birçok nesne Hizmetleri kapsüller. Türetilmiş tüm sınıflar `CObject` bu işlevselliği devralır.  
  
 Çalışma zamanı sınıf bilgilerine erişim, çalışma zamanında nesne sınıfı hakkında bilgi belirlemenize olanak sağlar. Çalışma zamanında bir nesne sınıfının belirleme özelliği ek türü denetimi işlev bağımsız değişkenleri ve bir nesne sınıfına göre özel amaçlı kodu yazarken gerekir gerektiğinde kullanışlıdır. Çalışma zamanı sınıf bilgileri doğrudan C++ dili tarafından desteklenmiyor.  
  
 Serileştirme için veya bir nesnenin içeriğini okuma veya yazma bir dosyadan işlemidir. Seri hale getirme bile uygulama çıktıktan sonra bir nesnenin içeriğini depolamak için kullanabilirsiniz. Uygulama yeniden başlatıldığında nesne sonra dosyayı okuyabilir. Bu tür veri nesneleri "kalıcı." olduğu söylenir  
  
 Dinamik Nesne oluşturma zamanında belirtilen sınıfın bir nesnesi oluşturmanıza olanak sağlar. Örneğin, belge, Görünüm ve çerçeve nesneleri framework dinamik olarak oluşturmak gerektiğinden, dinamik oluşturma desteklemelidir.  
  
 Aşağıdaki tabloda, çalışma zamanı sınıf bilgileri, seri hale getirme ve dinamik oluşturma desteği MFC makroları listeler.  
  
 Bu çalışma zamanı nesne Hizmetleri ve seri hale getirme hakkında daha fazla bilgi için bkz: [CObject sınıfı: çalışma zamanı sınıf bilgilerine erişme](../../mfc/accessing-run-time-class-information.md).  
  
### <a name="run-time-object-model-services-macros"></a>Çalışma zamanı nesne modeli Hizmetleri makroları  
  


|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|(Sınıfı bildiriminde kullanılmalıdır) çalışma zamanı sınıf bilgilerine erişim sağlar.|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|Dinamik oluşturma ve (sınıfı bildiriminde kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim sağlar.|  
|[DECLARE_SERIAL](#declare_serial)|Seri hale getirme ve (sınıfı bildiriminde kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim sağlar.|  
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|(Sınıfı uygulamasında kullanılmalıdır) çalışma zamanı sınıf bilgilerine erişim sağlar.|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Dinamik oluşturma ve (sınıfı uygulamasında kullanılmalıdır) çalışma zamanı bilgilerine erişim sağlar.|  
|[IMPLEMENT_SERIAL](#implement_serial)|Seri hale getirme ve (sınıfı uygulamasında kullanılmalıdır) çalışma süresi sınıf bilgilerine erişim verir.|  
|[RUNTIME_CLASS](#runtime_class)|Döndürür `CRuntimeClass` adlandırılmış sınıfına karşılık gelen yapısı.|  


 OLE nesneleri dinamik oluşturma zamanında sık gerektirir. Örneğin, bir sunucu uygulaması OLE öğeleri dinamik olarak isteğine yanıt olarak bir istemciden gelen oluşturabilecek gerekir. Benzer şekilde, Otomasyon sunucusu Otomasyon istemcilerden gelen isteklere yanıt öğeleri oluşturmak mümkün olması gerekir.  
  
 Microsoft Foundation Class Kitaplığı OLE için iki makrolar belirli sağlar.  
  
### <a name="dynamic-creation-of-ole-objects"></a>OLE nesneleri dinamik oluşturma  

 






|||  
|-|-|  
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Ortak Denetimler kitaplığı belirtilen API'yi uygulayan olup olmadığını belirler.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Ortak Denetimler kitaplığı belirtilen API'yi uygulayan olup olmadığını belirler.|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE Otomasyon yoluyla oluşturulacak nesneleri sağlar.|  
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Bildirir **Getusertypenameıd** ve `GetMiscStatus` denetim sınıfınızın üye işlevleri.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE denetim özelliklerini görüntülemek için özellik sayfalarının listesini sağlar bildirir.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE sistem tarafından oluşturulan nesneler sağlar.|  
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Implements **Getusertypenameıd** ve `GetMiscStatus` denetim sınıfınızın üye işlevleri.|  
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Ya da bu makrosu veya [ımplement_olecreate](#implement_olecreate) kullanan herhangi bir sınıf uygulama dosyada görünmelidir `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS
Ortak Denetimler kitaplığı belirtilen API'yi uygulayan olup olmadığını belirler.  
   
### <a name="syntax"></a>Sözdizimi  
  ```  
AFX_COMCTL32_IF_EXISTS(  proc );  
```
### <a name="parameters"></a>Parametreler  
 `proc`  
 İşlev adı içeren bir null ile sonlandırılmış dize işaretçi veya işlevin sıra sayısı değerini belirtir. Bu parametre bir sıra değeri ise, düşük düzey Word'de olmalıdır; yüksek düzey sözcük sıfır olmalıdır. Bu parametre, Unicode biçiminde olmalıdır.  
   
### <a name="remarks"></a>Açıklamalar  
 Ortak Denetimler kitaplığı tarafından işlevi belirtilen olup olmadığını belirlemek için bu makrosu kullanın `proc` (çağırmak yerine [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212).  
   
### <a name="requirements"></a>Gereksinimler  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ortak yalıtım denetimleri Kitaplığı](../isolation-of-the-mfc-common-controls-library.md) [afx_comctl32_ıf_exısts2](#afx_comctl32_if_exists2)
 
## <a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2
Ortak Denetimler kitaplığı belirtilen API'yi uygulayan olup olmadığını belirler (Bu Unicode sürümüdür [afx_comctl32_ıf_exısts](#afx_comctl32_if_exists)).  
   
### <a name="syntax"></a>Sözdizimi    
```  
AFX_COMCTL32_IF_EXISTS2( proc );  
```
### <a name="parameters"></a>Parametreler  
 `proc`  
 İşlev adı içeren bir null ile sonlandırılmış dize işaretçi veya işlevin sıra sayısı değerini belirtir. Bu parametre bir sıra değeri ise, düşük düzey Word'de olmalıdır; yüksek düzey sözcük sıfır olmalıdır. Bu parametre, Unicode biçiminde olmalıdır.  
   
### <a name="remarks"></a>Açıklamalar  
 Ortak Denetimler kitaplığı tarafından işlevi belirtilen olup olmadığını belirlemek için bu makrosu kullanın `proc` (çağırmak yerine [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212). Bu makrosu Unicode sürümüdür `AFX_COMCTL32_IF_EXISTS`.  
   
### <a name="requirements"></a>Gereksinimler  
 afxcomctl32.h, afxcomctl32.inl  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ortak yalıtım denetimleri Kitaplığı](../isolation-of-the-mfc-common-controls-library.md) [afx_comctl32_ıf_exısts](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 Bir nesnenin sınıfına ilişkin çalışma zamanı bilgileri bir sınıftan türetilirken erişim olanağı ekler `CObject`.  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekleme `DECLARE_DYNAMIC` sınıfı için üstbilgi (.h) modülü makrosuna sonra dahil bu modül, bu sınıfın nesnelere erişmesi gereken tüm .cpp modüllerin.  
  
 Kullanırsanız **DECLARE**_ **dinamik** ve `IMPLEMENT_DYNAMIC` açıklandığı gibi makroları sonra kullanabileceğiniz `RUNTIME_CLASS` makrosu ve `CObject::IsKindOf` işlevi nesneleriniz çalışma sınıfının belirlemek için süre.  
  
 Varsa `DECLARE_DYNAMIC` sınıfı bildiriminde, ardından dahil `IMPLEMENT_DYNAMIC` sınıfı uygulamasında eklenmesi gerekir.  
  
 Daha fazla bilgi için `DECLARE_DYNAMIC` makrosu, bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [ımplement_dynamıc](#implement_dynamic).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 Nesnelerin etkinleştirir `CObject`-türetilmiş sınıfları çalışma zamanında dinamik olarak oluşturulacak.  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve dinamik olarak yeni nesneler oluşturmak için bu özelliği kullanır. Yeni bir belgeyi açtığınızda, oluşturduğunuz Örneğin, yeni görünüm. Framework'te dinamik olarak oluşturmak gerektiğinden belge, Görünüm ve çerçeve sınıfları dinamik oluşturma desteklemelidir.  
  
 Ekleme `DECLARE_DYNCREATE` makrosu sınıfı için .h modülünde sonra dahil bu modül, bu sınıfın nesnelere erişmesi gereken tüm .cpp modüllerin.  
  
 Varsa `DECLARE_DYNCREATE` sınıfı bildiriminde, ardından dahil `IMPLEMENT_DYNCREATE` sınıfı uygulamasında eklenmesi gerekir.  
  
 Daha fazla bilgi için `DECLARE_DYNCREATE` makrosu, bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
> [!NOTE]
>  `DECLARE_DYNCREATE` Makrosu içeren tüm işlevselliğini `DECLARE_DYNAMIC`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [IMPLEMENT_DYNCREATE](#implement_dyncreate).  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

 
## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE
Bildirir **Getusertypenameıd** ve `GetMiscStatus` denetim sınıfınızın üye işlevleri.  
   
### <a name="syntax"></a>Sözdizimi    
```
DECLARE_OLECTLTYPE( class_name )  
```
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Denetim sınıfı adı.  
   
### <a name="remarks"></a>Açıklamalar  
 **Getusertypenameıd** ve `GetMiscStatus` bildirilen saf sanal işlevleri `COleControl`. Bu işlevler saf olduğundan sanal, bunlar denetim sınıfınızda geçersiz kılınmalıdır. Ek olarak **DECLARE_OLECTLTYPE**, eklemelisiniz `IMPLEMENT_OLECTLTYPE` denetim sınıf bildirimi makrosuna.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [IMPLEMENT_OLECTLTYPE](#implement_olectltype)
 

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS
OLE denetim özelliklerini görüntülemek için özellik sayfalarının listesini sağlar bildirir.  
   
### <a name="syntax"></a>Sözdizimi    
```
DECLARE_PROPPAGEIDS( class_name )  
```
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Özellik sayfaları sahibi control sınıfı adı.  
   
### <a name="remarks"></a>Açıklamalar  
 Kullanım `DECLARE_PROPPAGEIDS` makrosu sınıf bildiriminin sonundaki. Ardından, sınıf için üye işlevleri tanımlayan .cpp dosyasında kullanmak `BEGIN_PROPPAGEIDS` makrosu, makrosu girişleri denetiminizin özellik sayfaları, her ve `END_PROPPAGEIDS` özellik sayfası listesinin sonuna bildirmek için makrosu.  
  
 Özellik sayfaları hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: özellik sayfaları](../mfc-activex-controls-property-pages.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
   
### <a name="see-also"></a>Ayrıca Bkz.   
 [BEGIN_PROPPAGEIDS](#begin_proppageids)   
 [END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>DECLARE_SERIAL  
 C++ üstbilgi kodu için gerekli oluşturur bir `CObject`-türetilen seri hale getirilebilir sınıfı.  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Serileştirme için ve bir nesne içeriğini okuma veya yazma bir dosyadan işlemidir.  
  
 Kullanım `DECLARE_SERIAL` makrosu .h modülünde ve bu sınıfın nesnelere erişmesi gereken tüm .cpp modüllerin bu modülü içerir.  
  
 Varsa `DECLARE_SERIAL` sınıfı bildiriminde, ardından dahil `IMPLEMENT_SERIAL` sınıfı uygulamasında eklenmesi gerekir.  
  
 `DECLARE_SERIAL` Makrosu içeren tüm işlevselliğini `DECLARE_DYNAMIC` ve `DECLARE_DYNCREATE`.  
  
 Kullanabileceğiniz **AFX_API** otomatik olarak dışa aktarmak için makrosu `CArchive` ayıklama işleci için sınıfları kullanan `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları. Aşağıdaki kod sınıfı bildirimlerle (.h dosyasında bulunur) köşeli ayraç:  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Daha fazla bilgi için `DECLARE_SERIAL` makrosu, bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC  
 C++ kodu için dinamik gerekli oluşturur `CObject`-türetilmiş sınıf çalışma zamanı erişimi olan sınıf adı ve hiyerarşi içindeki konum.  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
 `base_class_name`  
 Taban sınıf adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `IMPLEMENT_DYNAMIC` makrosu .cpp modülü ve ardından bağlantıyı elde edilen nesnenin kod yalnızca bir kez.  
  
 Daha fazla bilgi için bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 Nesnelerin etkinleştirir `CObject`-türetilmiş sınıfları Çalıştır dinamik olarak oluşturulacak saat ile kullanıldığında `DECLARE_DYNCREATE` makrosu.  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
 `base_class_name`  
 Taban sınıfı gerçek adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bu özelliği bir nesne seri hale getirme sırasında diskten okuduğunda yeni nesneler dinamik olarak, örneğin, oluşturmak için kullanır. Ekleme `IMPLEMENT_DYNCREATE` sınıfı uygulama dosyasındaki makro. Daha fazla bilgi için bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
 Kullanırsanız `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE` makroları, sonra kullanabileceğiniz `RUNTIME_CLASS` makrosu ve `CObject::IsKindOf` üye işlevi nesneleriniz sınıfının çalışma zamanında belirlemek için.  
  
 Varsa `DECLARE_DYNCREATE` sınıfı bildiriminde, ardından dahil `IMPLEMENT_DYNCREATE` sınıfı uygulamasında eklenmesi gerekir.  
  
 Bu bir makro tanımı sınıfınız için varsayılan oluşturucu çağıracağı unutmayın. Önemsiz olmayan bir oluşturucu sınıfı tarafından açıkça uygulanmışsa, aynı zamanda açıkça varsayılan oluşturucu de uygulamalıdır. Varsayılan Oluşturucu sınıfına ait eklenebilir **özel** veya **korumalı** gelen dışında sınıf uygulamasını çağrılan gelen önlemek için üye bölümler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

## <a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS
Ya da bu makrosu veya [ımplement_olecreate](#implement_olecreate) kullanan herhangi bir sınıf uygulama dosyada görünmelidir `DECLARE_OLECREATE`.  
   
### <a name="syntax"></a>Sözdizimi    
```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags, 
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
  
```
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
 *external_name*  
 (Tırnak işaretleri içine) diğer uygulamaları maruz nesne adı.  
  
 `nFlags`  
 Bir veya daha fazla aşağıdaki bayraklar içerir:  
  
-   `afxRegInsertable`OLE nesneleri için Nesne Ekle iletişim kutusunda görünmesi denetimi sağlar.    
-   `afxRegApartmentThreading`İş parçacığı modelini ThreadingModel için kayıt defterindeki ayarlar Grup =.    
-   **afxRegFreeThreading** ThreadingModel için kayıt defterindeki iş parçacığı modelini ayarlar serbest =.  
  
     İki bayrak birleştirebilirsiniz `afxRegApartmentThreading` ve `afxRegFreeThreading` ThreadingModel ayarlamak için her ikisini de =. Bkz: [Inprocserver32](http://msdn.microsoft.com/library/windows/desktop/ms682390) modeli kaydı iş parçacığı oluşturma hakkında daha fazla bilgi için Windows SDK'sındaki.    
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 Sınıfının bileşenlerinin **CLSID**.  
   
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Kullanırsanız `IMPLEMENT_OLECREATE_FLAGS`, nesnenizin destekleyen kullanarak hangi iş parçacığı modelini belirtebilirsiniz `nFlags` parametresi. Yalnızca tek treading modeli desteklemek istiyorsanız, kullanmak `IMPLEMENT_OLECREATE`.  
  
 Dış ad başka uygulamalar için kullanıma sunulan tanımlayıcıdır. İstemci uygulamaları dış adı bu sınıfın bir nesnesi bir Otomasyon sunucusundan istemek için kullanın.  
  
 OLE sınıfı kimliği benzersiz bir nesne 128-bit tanımlayıcısıdır. Aşağıdakilerden birini oluşur **uzun**, iki **WORD**s ve sekiz **bayt**tarafından temsil edilen s *l*, *w1*, *w2*, ve *b1* aracılığıyla *b8* sözdizimi açıklaması. Uygulama Sihirbazı'nı ve kod sihirbazları benzersiz OLE sınıf kimlikleri sizin için gerektiği şekilde oluşturun.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [DECLARE_OLECREATE](#declare_olecreate)   
 [CLSID anahtarı](http://msdn.microsoft.com/library/windows/desktop/ms691424)


## <a name="implement_olecreate"></a>IMPLEMENT_OLECTLTYPE
Implements **Getusertypenameıd** ve `GetMiscStatus` denetim sınıfınızın üye işlevleri.  
   
### <a name="syntax"></a>Sözdizimi    
```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )  
```
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Denetim sınıfı adı.  
  
 *idsUserTypeName*  
 Denetimin dış adını içeren bir dize kaynak kimliği.  
  
 *dwOleMisc*  
 Bir veya daha fazla bayrak içeren numaralandırması. Bu numaralandırma hakkında daha fazla bilgi için bkz: [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Windows SDK'sındaki.  
   
### <a name="remarks"></a>Açıklamalar  
 Ek olarak `IMPLEMENT_OLECTLTYPE`, eklemelisiniz **DECLARE_OLECTLTYPE** denetim sınıf bildirimi makrosuna.  
  
 **Getusertypenameıd** üye işlevi denetim sınıfınıza tanımlayan kaynak dize döndürür. `GetMiscStatus`döndürür **OLEMISC** BITS denetlemek için. Bu numaralandırma denetiminizi çeşitli özelliklerini açıklayan ayarlar koleksiyonu belirtir. Tam açıklama için **OLEMISC** bkz: ayarlar, [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Windows SDK'sındaki.  
  
> [!NOTE]
>  ActiveX ControlWizard tarafından kullanılan varsayılan ayarlar şunlardır: **OLEMISC_ACTIVATEWHENVISIBLE**, **OLEMISC_SETCLIENTSITEFIRST**, **OLEMISC_INSIDEOUT**, **OLEMISC_CANTLINKINSIDE**, ve **OLEMISC_RECOMPOSEONRESIZE**.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxctl.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>IMPLEMENT_SERIAL  
 C++ kodu için dinamik gerekli oluşturur `CObject`-türetilmiş sınıf çalışma zamanı erişimi olan sınıf adı ve hiyerarşi içindeki konum.  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
 `base_class_name`  
 Taban sınıf adı.  
  
 *wSchema*  
 A **UINT** "tanımlamak ve tarafından oluşturulan verileri işlemek kaldırırken bir programı etkinleştirmek için arşivde kodlanmış sürüm numarası" önceki sürümleri program. Sınıf şema sayısı -1 olamaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `IMPLEMENT_SERIAL` makrosu .cpp modülünde; sonuçta elde edilen nesne kodu yalnızca bir kez bağlantı.  
  
 Kullanabileceğiniz **AFX_API** otomatik olarak dışa aktarmak için makrosu `CArchive` ayıklama işleci için sınıfları kullanan `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları. Aşağıdaki kod sınıfı bildirimlerle (.h dosyasında bulunur) köşeli ayraç:  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 Daha fazla bilgi için bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 

##  <a name="runtime_class"></a>RUNTIME_CLASS  
 Çalışma zamanı sınıf yapısında bir C++ sınıf adından alır.  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 (Tırnak işaretleri içine değil) sınıfının gerçek adı.  
  
### <a name="remarks"></a>Açıklamalar  
 `RUNTIME_CLASS`bir işaretçi döndüren bir [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) tarafından belirtilen sınıfı için yapısı *class_name*. Yalnızca `CObject`-türetilmiş sınıflar ile bildirilen `DECLARE_DYNAMIC`, `DECLARE_DYNCREATE`, veya `DECLARE_SERIAL` işaretçileri döndürülecek bir `CRuntimeClass` yapısı.  
  
 Daha fazla bilgi için bkz: [CObject sınıfı konuları](../../mfc/using-cobject.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h 
   
##  <a name="declare_olecreate"></a>DECLARE_OLECREATE  
 Nesnelerin etkinleştirir `CCmdTarget`-türetilmiş OLE Otomasyon yoluyla oluşturulacak sınıflar.  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro bu tür nesneler oluşturmak diğer OLE özellikli uygulamalar sağlar.  
  
 Ekleme `DECLARE_OLECREATE` sınıfı için .h modülünde makrosu ve bu sınıfın nesnelere erişmesi gereken tüm .cpp modüllerin bu modülü içerir.  
  
 Varsa `DECLARE_OLECREATE` sınıfı bildiriminde, ardından dahil `IMPLEMENT_OLECREATE` sınıfı uygulamasında eklenmesi gerekir. Sınıf bildirimi kullanarak `DECLARE_OLECREATE` de kullanmanız gerekir `DECLARE_DYNCREATE` veya `DECLARE_SERIAL`.  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h  

##  <a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 Ya da bu makrosu veya [ımplement_olecreate_flags](#implement_olecreate_flags) kullanan herhangi bir sınıf uygulama dosyada görünmelidir `DECLARE_OLECREATE`.  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sınıfının gerçek adı.  
  
 *external_name*  
 (Tırnak işaretleri içine) diğer uygulamaları maruz nesne adı.  
  
 *l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*  
 Sınıfının bileşenlerinin **CLSID**.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Kullanırsanız `IMPLEMENT_OLECREATE`, varsayılan olarak, yalnızca tek iş parçacığı modelini destekler. Kullanırsanız `IMPLEMENT_OLECREATE_FLAGS`, nesnenizin destekleyen kullanarak hangi iş parçacığı modelini belirtebilirsiniz `nFlags` parametresi.  
  
 Dış ad başka uygulamalar için kullanıma sunulan tanımlayıcıdır. İstemci uygulamaları dış adı bu sınıfın bir nesnesi bir Otomasyon sunucusundan istemek için kullanın.  
  
 OLE sınıfı kimliği benzersiz bir nesne 128-bit tanımlayıcısıdır. Aşağıdakilerden birini oluşur **uzun**, iki **WORD**s ve sekiz **bayt**tarafından temsil edilen s *l*, *w1*, *w2*, ve *b1* aracılığıyla *b8* sözdizimi açıklaması. Uygulama Sihirbazı'nı ve kod sihirbazları benzersiz OLE sınıf kimlikleri sizin için gerektiği şekilde oluşturun.  

### <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: afxdisp.h 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)

