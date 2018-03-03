---
title: "Standart iletişim kutusu veri değişimi yordamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data exchange routines
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca598a9ac6a146457d24bcc80e54d003123d7dd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="standard-dialog-data-exchange-routines"></a>Standart İletişim Kutusu Veri Değişimi Rutinleri
Bu konu genel MFC iletişim kutusu denetimleri için kullanılan standart iletişim kutusu veri değişimi (DDX) yordamları listeler.  
  
> [!NOTE]
>  Standart iletişim kutusu veri değişimi rutinleri üstbilgi dosyası afxdd_.h tanımlanır. Ancak, uygulamaları afxwin.h içermelidir.  
  
### <a name="ddx-functions"></a>DDX işlevleri  
  
|||  
|-|-|  
|[Ddx_cbındex](#ddx_cbindex)|Birleşik giriş kutusu denetimi, geçerli seçim dizinini alır veya başlatır.|  
|[DDX_CBString](#ddx_cbstring)|Birleşik giriş kutusu denetimi Düzenle alanının geçerli içeriğini alır veya başlatır.|  
|[DDX_CBStringExact](#ddx_cbstringexact)|Birleşik giriş kutusu denetimi Düzenle alanının geçerli içeriğini alır veya başlatır.|  
|[DDX_Check](#ddx_check)|Bir onay kutusu denetimi geçerli durumunu alır veya başlatır.|  
|[DDX_Control](#ddx_control)|Alt sınıfların bir iletişim kutusu içinde belirli bir denetim.|  
|[DDX_DateTimeCtrl](#ddx_datetimectrl)|Başlatır veya bir tarih ve Saat Seçici denetiminin tarih ve/veya saat verileri alır.|  
|[Ddx_ıpaddress](#ddx_ipaddress)|Bir IP adresi denetimi geçerli değeri alır veya başlatır.|  
|[Ddx_lbındex](#ddx_lbindex)|Liste kutusu denetimi, geçerli seçim dizinini alır veya başlatır.|  
|[DDX_LBString](#ddx_lbstring)|Geçerli seçim içindeki bir liste kutusu denetimini alır veya başlatır.|  
|[DDX_LBStringExact](#ddx_lbstringexact)|Geçerli seçim içindeki bir liste kutusu denetimini alır veya başlatır.|
|[DDX_ManagedControl](#ddx_managedcontrol)|Denetimin kaynak kimlikle eşleşen bir .NET denetimi oluşturur|  
|[DDX_MonthCalCtrl](#ddx_monthcalctrl)|Aylık takvim denetiminin geçerli değeri alır veya başlatır.|  
|[DDX_Radio](#ddx_radio)|Şu anda radyo denetim Grup içinde kullanıma radyo denetim 0 tabanlı dizinini alır veya başlatır.|  
|[DDX_Scroll](#ddx_scroll)|Bir kaydırma denetimin kaydırma geçerli konumunu alır veya başlatır.|  
|[DDX_Slider](#ddx_slider)|Kaydırıcı denetim Flash geçerli konumunu alır veya başlatır.|  
|[DDX_Text](#ddx_text)|Bir düzen denetimi geçerli değeri alır veya başlatır.|  
  
##  <a name="ddx_cbindex"></a>Ddx_cbındex  
 `DDX_CBIndex` İşlevi aktarımını yönetir `int` arasında bir iletişim kutusu, birleşik giriş kutusu denetiminde veri form görünümü ya da Denetim Görünüm nesnesi ve `int` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_CBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Birleşik giriş kutusu denetimi denetim özelliğiyle ilişkili kaynak kimliği.  
  
 *Dizin*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_CBIndex` olarak adlandırılır, *dizin* geçerli birleşik giriş kutusu seçimi dizinine ayarlanır. Öğe seçiliyse, *dizin* 0 olarak ayarlayın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_cbstring"></a>DDX_CBString  
 `DDX_CBString` İşlevi aktarımını yönetir `CString` birleşik giriş kutusu denetiminde bir iletişim kutusu düzen denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `CString` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_CBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Birleşik giriş kutusu denetimi denetim özelliğiyle ilişkili kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_CBString` olarak adlandırılır, *değeri* geçerli birleşik giriş kutusu seçimi ayarlayın. Öğe seçiliyse, *değeri* sıfır uzunlukta bir dize olarak ayarlayın.  
  
> [!NOTE]
>  Birleşik giriş kutusu açılan liste kutusu ise, değiştirilen 255 karakterle sınırlı değerdir.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_cbstringexact"></a>DDX_CBStringExact  
 `DDX_CBStringExact` İşlevi aktarımını yönetir `CString` birleşik giriş kutusu denetiminde bir iletişim kutusu düzen denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `CString` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_CBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Birleşik giriş kutusu denetimi denetim özelliğiyle ilişkili kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_CBStringExact` olarak adlandırılır, *değeri* geçerli birleşik giriş kutusu seçimi ayarlayın. Öğe seçiliyse, *değeri* sıfır uzunlukta bir dize olarak ayarlayın.  
  
> [!NOTE]
>  Birleşik giriş kutusu açılan liste kutusu ise, değiştirilen 255 karakterle sınırlı değerdir.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_check"></a>DDX_Check  
 `DDX_Check` İşlevi aktarımını yönetir `int` iletişim kutusunda, onay kutusu denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `int` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_Check(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özellik ile ilişkilendirilmiş onay kutusu denetimi kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_Check` olarak adlandırılır, *değeri* onay kutusu denetimi geçerli durumuna ayarlanır. Olası durum değerlerinin listesi için bkz: [BM_GETCHECK](http://msdn.microsoft.com/library/windows/desktop/bb775986) Windows SDK'sındaki.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_control"></a>DDX_Control  
 `DDX_Control` Alt sınıflar tarafından belirtilen denetim işlev `nIDC`, iletişim kutusu, form görünümü veya denetim görünüm nesnesi.  
  
```  
void AFXAPI DDX_Control(
    CDataExchange* pDX,  
    int nIDC,  
    CWnd& rControl);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi.  
  
 `nIDC`  
 Kaynak Kimliği sınıflandırma denetimi.  
  
 *rControl*  
 Üye değişkeni iletişim kutusu, form görünümü veya denetim görünüm nesnesi belirtilen denetimi ile ilgili başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 `pDX` Nesne çerçevesi tarafından sağlanan zaman `DoDataExchange` işlevi çağrılır. Bu nedenle, `DDX_Control` geçersiz kılma içinde yalnızca çağrılmalıdır `DoDataExchange`.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_datetimectrl"></a>DDX_DateTimeCtrl  
 `DDX_DateTimeCtrl` İşlevi bir tarih ve Saat Seçici denetimini arasında tarih ve/veya saat veri aktarımını yönetir ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) bir iletişim kutusu veya form görünümü nesnesi ve ya da bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) iletişim kutusu veya form görünümü nesnesi veri üyesi.  
  
```  
void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);

void AFXAPI DDX_DateTimeCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar. Bu nesneyi silmek gerek yoktur.  
  
 `nIDC`  
 Üye değişkeni ile ilişkilendirilmiş tarih ve Saat Seçici denetimini kaynak kimliği.  
  
 *value*  
 İlk iki sürümlerinde, bir başvuru bir `CTime` veya `COleDateTime` üye değişkeni, iletişim kutusu, form görünümü veya ile veri değişimi denetim görünüm nesnesi. Bir başvuru üçüncü sürümündeki bir `CString` veri üyesi denetim görünüm nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_DateTimeCtrl` olarak adlandırılır, *değeri* geçerli ayarlamak tarih ve Saat Seçici denetimini veya denetim durumu ayarlanmış *değeri*exchange yönünü bağlı olarak.  
  
 Yukarıdaki üçüncü sürümünde `DDX_DateTimeCtrl` aktarımını yönetir `CString` verileri arasında bir tarih saat denetim ve [CString](../../atl-mfc-shared/reference/cstringt-class.md) denetim görünüm nesnesi veri üyesi. Tarihler ve saatler biçimlendirme için geçerli yerel kurallarını kullanarak biçimlendirilmiş dize.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  

   

 
## <a name="ddx_managedcontrol"></a>DDX_ManagedControl
Denetimin kaynak kimlikle eşleşen bir .NET denetimi oluşturur  
   
### <a name="syntax"></a>Sözdizimi  
  ```  
template <typename T>  
void DDX_ManagedControl(  
     CDataExchange* pDX,   
     int nIDC,   
     CWinFormsControl<T>& control );  
```
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange sınıfı](cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özelliği ile ilişkili denetime kaynak kimliği.  
  
 `control`  
 Bir başvuru bir [Ddx_managedcontrol sınıfı](cwinformscontrol-class.md) nesnesi.  
   
### <a name="remarks"></a>Açıklamalar  
 `DDX_ManagedControl`çağrıları [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol) kaynak denetimi kimlikle eşleşen bir denetim oluşturmak için Kullanım `DDX_ManagedControl` kaynak kimlikleri denetimleri oluşturmak için [CDialog::OnInitDialog](cdialog-class.md#oninitdialog). Veri değişimi için Windows Forms denetimleri ile DDX/DDV işlevlerini kullanmak gerekmez.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: yapmak DDX/DDV veri bağlaması Windows Forms ile](../../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [CWinFormsControl::CreateManagedControl](cwinformscontrol-class.md#createmanagedcontrol)   
 [CDialog::OnInitDialog](cdialog-class.md#oninitdialog)
 

  
##  <a name="ddx_ipaddress"></a>Ddx_ıpaddress  
 `DDX_IPAddress` İşlevi bir IP adresi denetimini ve denetim görünüm nesnesi veri üyesi arasında veri aktarımını yönetir.  
  
```  
void AFXAPI DDX_IPAddress(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özelliği ile ilişkili IP adresi denetim kaynak kimliği.  
  
 *value*  
 Bir başvuru `DWORD` IP adresi denetim dört alanı değerini içeren. Alanları doldurulmuş veya gibi görünecek.  
  
|Alan|Alan değeri içeren BITS|  
|-----------|-------------------------------------|  
|3|0 ile 7 arasında|  
|2|8-15|  
|1.|23 aracılığıyla 16|  
|0|24 ile 31 arasında|  
  
 Win32 kullanmak [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378) değer okuma veya kullanma [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380) değeri doldurmak için. Bu iletiler, Windows SDK'ın açıklanmıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_IPAddress` olarak adlandırılır, *değeri* ya da IP adresi denetiminden okuma veya *değeri* exchange yöne bağlı olarak denetim yazılır.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_lbindex"></a>Ddx_lbındex  
 `DDX_LBIndex` İşlevi aktarımını yönetir `int` iletişim kutusunda, liste kutusu denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve bir `int` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_LBIndex(
    CDataExchange* pDX,  
    int nIDC,  
    int& index);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özellik ile ilişkilendirilmiş liste kutusu denetimini kaynak kimliği.  
  
 *Dizin*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_LBIndex` olarak adlandırılır, *dizin* geçerli liste kutusu seçimine dizinine ayarlanır. Öğe seçiliyse, *dizin* -1 olarak ayarlayın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_lbstring"></a>DDX_LBString  
 `DDX_LBString` İşlevi aktarımını yönetir `CString` iletişim kutusunda, liste kutusu denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `CString` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_LBString(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özellik ile ilişkilendirilmiş liste kutusu denetimini kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_LBString` liste kutusu denetimi, listedeki ilk öğe olan başına eşleşen denetim veri aktarmak için adlı *değeri* seçilir. (Yalnızca bir önek yerine öğenin tamamı eşleşecek şekilde kullanmak [DDX_LBStringExact](#ddx_lbstringexact).) Herhangi bir eşleşme varsa, hiç öğe seçilmedi. Eşleştirme büyük küçük harfe duyarlıdır.  
  
 Zaman `DDX_LBString` bir liste kutusu denetimi veri aktarmak için adlı *değeri* geçerli liste kutusu seçimi ayarlayın. Öğe seçiliyse, *değeri* sıfır uzunlukta bir dize olarak ayarlayın.  
  
> [!NOTE]
>  Liste kutusunda aşağı açılan liste kutusu ise, değiştirilen 255 karakterle sınırlı değerdir.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_lbstringexact"></a>DDX_LBStringExact  
 `DDX_CBStringExact` İşlevi aktarımını yönetir `CString` iletişim kutusunda, bir liste kutusu denetiminin düzenleme denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `CString` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_LBStringExact(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özellik ile ilişkilendirilmiş liste kutusu denetimini kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_LBStringExact` liste kutusu denetimi, listedeki ilk öğe ile eşleşen denetim veri aktarmak için adlı *değeri* seçilir. (Öğenin tamamı yerine yalnızca bir önek eşleşecek şekilde kullanmak [DDX_LBString](#ddx_lbstring).) Herhangi bir eşleşme varsa, hiç öğe seçilmedi. Eşleştirme büyük küçük harfe duyarlıdır.  
  
 Zaman `DDX_CBStringExact` bir liste kutusu denetimi veri aktarmak için adlı *değeri* geçerli liste kutusu seçimi ayarlayın. Öğe seçiliyse, *değeri* sıfır uzunlukta bir dize olarak ayarlayın.  
  
> [!NOTE]
>  Liste kutusunda aşağı açılan liste kutusu ise, değiştirilen 255 karakterle sınırlı değerdir.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_monthcalctrl"></a>DDX_MonthCalCtrl  
 `DDX_MonthCalCtrl` İşlevi bir aylık takvim denetiminin arasında tarih veri aktarımını yönetir ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) bir iletişim kutusu, form görünümünde veya denetim görünüm nesnesi ve ya da bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) veya bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    CTime& value);

void AFXAPI DDX_MonthCalCtrl(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar. Bu nesneyi silmek gerek yoktur.  
  
 `nIDC`  
 Aylık takvim denetiminin kaynak Kimliğini üye değişkeni ile ilişkilendirilmiş.  
  
 *value*  
 Bir başvuru bir `CTime` veya `COleDateTime` üye değişkeni iletişim kutusu, form görünümü veya ile veri değişimi denetim görünüm nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Denetim bir tarih değeri yalnızca yönetir. Zaman zaman nesnesindeki denetimi penceresi oluşturulma zamanını yansıtacak şekilde ayarlama veya her zaman çağrısıyla denetiminde ayarlandı alanlardır `CMonthCalCtrl::SetCurSel`.  
  
 Zaman `DDX_MonthCalCtrl` olarak adlandırılır, *değeri* aylık takvim denetiminin geçerli durumuna ayarlanır.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_radio"></a>DDX_Radio  
 `DDX_Radio` İşlevi aktarımını yönetir `int` iletişim kutusundaki radyo denetim grubu arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `int` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi. Değeri `int` veri üyesi olduğunu belirledi göre hangi radyo düğmesi grubundaki seçilir.  
  
```  
void AFXAPI DDX_Radio(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Gruptaki ilk radyo denetimi kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_Radio` olarak adlandırılır, *değeri* radyo denetim grubu geçerli durumuna ayarlanır. Değer bir 0 tabanlı bir dizin şu anda kullanıma radyo denetimi ayarlanır veya hiçbir radyo denetimleri, -1 denetlenir.  
  
 Örneğin, ilk radyo düğmesi grubunda durumda değerini (WS_GROUP stiliyle düğmesi) kullanıma `int` üyesidir 0 ve benzeri.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_scroll"></a>DDX_Scroll  
 `DDX_Scroll` İşlevi aktarımını yönetir `int` bir iletişim kutusunda kaydırma çubuğu denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve bir `int` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_Scroll(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özellik ile ilişkilendirilmiş kaydırma çubuğu denetimi kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_Scroll` olarak adlandırılır, *değeri* denetimin kaydırma geçerli konumunu ayarlayın. Denetimin kaydırma geçerli konumu ile ilişkili değerler hakkında daha fazla bilgi için bkz: [GetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787585) Windows SDK'sındaki.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_slider"></a>DDX_Slider  
 `DDX_Slider` İşlevi aktarımını yönetir `int` kaydırıcı denetimi iletişim kutusunu veya form görünümünde arasında veri ve bir `int` iletişim kutusu veya form görünümü nesnesi veri üyesi.  
  
```  
void AFXAPI DDX_Slider(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Kaydırıcı denetimi kaynak kimliği.  
  
 *value*  
 Değiştirilebilmesi için değeri referansı. Bu parametre tutan veya kaydırıcı denetimin geçerli konumunu ayarlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_Slider` olarak adlandırılır, *değeri* denetimin kaydırma kutusu, geçerli konuma ayarlayın veya exchange yöne bağlı olarak konum değeri alır.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz: [kullanarak CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  
  
##  <a name="ddx_text"></a>DDX_Text  
 `DDX_Text` İşlevi aktarımını yönetir `int`, **UINT**, **uzun**, `DWORD`, `CString`, **float**, veya  **çift** arasında bir iletişim kutusu, Düzen denetiminde veri form görünümü ya da Denetim görünümü ve bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    BYTE& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    short& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    int& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    UINT& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    long& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    DWORD& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    CString& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    float& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    double& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleCurrency& value);

void AFXAPI DDX_Text(
    CDataExchange* pDX,  
    int nIDC,  
    COleDateTime& value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir düzen denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 *value*  
 İletişim kutusunda, form görünümü veya denetim görünüm nesnesi veri üyesine bir başvuru. Veri türü *değeri* bağımlı olduğu aşırı yüklenmiş sürümlerinin `DDX_Text` kullanın.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdd_.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Standart iletişim kutusu veri doğrulama rutinleri](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
