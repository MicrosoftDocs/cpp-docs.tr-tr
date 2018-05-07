---
title: Temsilci ile arabirimi eşleme makroları (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1e6f2e8cc501f9a466e4970d27a2e6ecd9174ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
|||  
|-|-|  
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|Bir temsilci harita başlar.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|İnterfaced harita tanımını başlar.|
|[CommandHandler temsilcisi](#commandhandler)|Geri arama yöntemleri komut kaynağı ile kaydeder.  |
|[END_DELEGATE_MAP](#end_delegate_map)|Bir temsilci harita sona erer.|
|[END_INTERFACE_MAP](#end_interface_map)|Uygulama dosyasını arabirimi eşlemesinde sona erer. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|Bir giriş temsilci eşlemesinde oluşturur.|
|[INTERFACE_PART](#interface_part)|Arasında kullanılan `BEGIN_INTERFACE_MAP` makrosu ve `END_INTERFACE_MAP` nesnenizin makrosu her arabirim için destekler.|
|[MAKE_DELEGATE](#make_delegate)|Bir olay işleyicisi için yönetilen bir denetimin ekler.|


## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP
Bir temsilci harita başlar.  
   
### <a name="syntax"></a>Sözdizimi    
```  
BEGIN_DELEGATE_MAP(  CLASS );  
```
### <a name="parameters"></a>Parametreler  
 `CLASS`  
 Yönetilen denetim barındırılan sınıf.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu bir temsilci eşlemesi oluşturma temsilci girişlerinin listesini başlangıcını işaretler. Bu makrosu nasıl kullanıldığına ilişkin bir örnek için bkz: [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** msclr\event.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)
 
##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP
Uygulama dosyasında kullanıldığında interfaced harita tanımını başlar.  
   
### <a name="syntax"></a>Sözdizimi    
```
BEGIN_INTERFACE_MAP( theClass, baseClass )  
```
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Arabirim eşlemesi tanımlanacak olduğu sınıfı  
  
 `baseClass`  
 Sınıfından `theClass` türetir.  
   
### <a name="remarks"></a>Açıklamalar  
 Uygulanan her arabirim için var olan bir veya daha fazla `INTERFACE_PART` makrosu çağrılarını. Sınıfını kullanan her toplama için bir olduğundan **INTERFACE_AGGREGATE** makrosu çağırma.  
  
 Arabirim eşlemeleri hakkında daha fazla bilgi için bkz: [Teknik Not 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
 
##  <a name="commandhandler"></a>CommandHandler temsilcisi
Geri arama yöntemleri komut kaynağı ile kaydeder.  
   
### <a name="syntax"></a>Sözdizimi    
```  
delegate void CommandHandler(  UINT^ cmdID  );  
```
### <a name="parameters"></a>Parametreler  
 `cmdID`  
 Komut kimliği.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu temsilci geri arama yöntemleri komut kaynağı ile kaydeder. Komut kaynak nesnesi için bir temsilci eklediğinizde, geri çağırma yöntemi belirtilen kaynağından gelen komutları için bir işleyici haline gelir.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme eklemek](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md).  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)
 
##  <a name="commanduihandler"></a>Commanduıhandler
Geri arama yöntemleri içeren bir kullanıcı arabirimi güncelleştirme komut ileti kaydeder.  
   
### <a name="syntax"></a>Sözdizimi    
```  
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);  
```
### <a name="parameters"></a>Parametreler  
 `cmdID`  
 Komut kimliği.  
  
 `cmdUI`  
 Komut ileti kimliği.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu temsilci geri arama yöntemleri içeren bir kullanıcı arabirimi güncelleştirme komut ileti kaydeder. `CommandUIHandler` benzer [CommandHandler](#commandhandler) dışında bu temsilciyi kullanıcı arabirimi nesne güncelleştirme komutları ile kullanılır. Kullanıcı arabirimi güncelleştirme komutları bire bir ileti işleyicisi yöntemleri ile eşlenmelidir.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll tanımlanan)  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: komut ekleme yönlendirme Windows Forms denetimi](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP
Bir temsilci harita sona erer.  
   
### <a name="syntax"></a>Sözdizimi    
```  
END_DELEGATE_MAP();  
```  
   
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu bir temsilci eşlemesi oluşturma temsilci girişlerinin listesini sonunu işaretler. Bu makrosu nasıl kullanıldığına ilişkin bir örnek için bkz: [EVENT_DELEGATE_ENTRY](#event_delegate_entry).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** msclr\event.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  

 [Nasıl yapılır: Yerel C++ Sınıflarından İç Havuz Windows Forms Olayları](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

 
##  <a name="end_interface_map"></a>END_INTERFACE_MAP
Uygulama dosyasını arabirimi eşlemesinde sona erer.  
   
### <a name="syntax"></a>Sözdizimi    
```
END_INTERFACE_MAP( )    
```  
   
### <a name="remarks"></a>Açıklamalar  
 Arabirim eşlemeleri hakkında daha fazla bilgi için bkz: [Teknik Not 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [BEGIN_INTERFACE_MAP](#begin_interface_map)
 

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY
Bir giriş temsilci eşlemesinde oluşturur.  
   
### <a name="syntax"></a>Sözdizimi    
```  
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);  
```
### <a name="parameters"></a>Parametreler  
 `MEMBER`  
 Denetime ekli olay işleyicisi yöntemi.  
  
 `ARG0`  
 Yönetilen olay işleyicisi yönteminin ilk bağımsız değişkeni gibi **nesne ^**.  
  
 `ARG1`  
 Yönetilen olay işleyicisi yönteminin ikinci bağımsız değişkeni gibi **EventArgs ^**.  
   
### <a name="remarks"></a>Açıklamalar  
 Her giriş temsilci eşlemesindeki tarafından oluşturulan bir yönetilen olay işleyici temsilcisi karşılık gelen [MAKE_DELEGATE](#make_delegate).  
   
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir `EVENT_DELEGATE_ENTRY` bir girdi için temsilci eşlemesi oluşturmak için `OnClick` olay işleyicisi; ayrıca aşağıdaki kod örneğinde bkz `MAKE_DELEGATE`. Daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuzu](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
 ```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** msclr\event.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [MAKE_DELEGATE](#make_delegate)   
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)
 

##  <a name="interface_part"></a>INTERFACE_PART
Arasında kullanılan `BEGIN_INTERFACE_MAP` makrosu ve `END_INTERFACE_MAP` nesnenizin makrosu her arabirim için destekler.  
   
### <a name="syntax"></a>Sözdizimi    
```
INTERFACE_PART( theClass, iid, localClass)  
```
### <a name="parameters"></a>Parametreler  
 `theClass`  
 Arabirim eşlemesi içeren sınıfın adı.    
 `iid`  
 Katıştırılmış sınıfına eşlenecek IID.    
 *localClass*  
 Yerel sınıfın adı.  
   
### <a name="remarks"></a>Açıklamalar  
 Belirtilen sınıf üyesi için bir IID eşlemenizi sağlar `theClass` ve *localClass*.  
  
 Arabirim eşlemeleri hakkında daha fazla bilgi için bkz: [Teknik Not 38](../tn038-mfc-ole-iunknown-implementation.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
   
 
##  <a name="make_delegate"></a>MAKE_DELEGATE
Bir olay işleyicisi için yönetilen bir denetimin ekler.  
   
### <a name="syntax"></a>Sözdizimi    
```  
MAKE_DELEGATE( DELEGATE,  MEMBER) ;  
```
### <a name="parameters"></a>Parametreler  
 `DELEGATE`  
 Gibi yönetilen olay işleyicisinin türü temsilci [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True).  
  
 `MEMBER`  
 Denetime ekli olay işleyicisi yöntemi adı.  
   
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu türü bir yönetilen olay işleyici temsilcisi oluşturur `DELEGATE` ve adının `MEMBER`. Yönetilen olay işleyici temsilcisi yönetilen olayları işlemek için yerel bir sınıf sağlar.  
   
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl çağrılacağını gösterir `MAKE_DELEGATE` eklemek için bir `OnClick` bir MFC denetlemek için olay işleyicisini `MyControl`. Bir MFC uygulamasında bu makrosu nasıl çalıştığını daha geniş açıklaması için bkz [nasıl yapılır: Windows Forms olayları yerel C++ sınıflarından havuzu](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md).  
  
```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** msclr\event.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)
 



