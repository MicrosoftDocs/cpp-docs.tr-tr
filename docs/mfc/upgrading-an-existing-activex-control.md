---
title: Varolan bir ActiveX denetimini güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e40240367d3e8350cee030b2c08dc5a48325e05f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385313"
---
# <a name="upgrading-an-existing-activex-control"></a>Varolan Bir ActiveX Denetimini Güncelleştirme
Varolan ActiveX denetimleri (önceki adıyla OLE denetimleri) değişiklik yapmadan Internet üzerinde kullanılabilir. Ancak, kendi performansını artırmak için denetimleri değiştirmek isteyebilirsiniz. Bir Web sayfası denetiminizde kullanırken dikkat edilecek diğer noktalar vardır. .Ocx dosyasını ve tüm destekleyici dosyaları hedef makinede olmalıdır veya Internet üzerinden indirilmesi. Bu kod boyutu ve önemli bir konu zaman yükleme sağlar. İndirmeler imzalı .cab dosyasında paketlenebilir. Denetim kodlama için güvenli olarak ve başlatma için güvenli olarak işaretleyebilirsiniz.  
  
 Bu makalede aşağıdaki konular ele alınmıştır:  
  
- [İndirme için kodu paketleme](#_core_packaging_code_for_downloading)  
  
- [Komut dosyası oluşturma ve başlatma için bir denetim güvenli işaretleme](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
- [Lisans sorunları](#_core_licensing_issues)  
  
- [Kod imzalama](#_core_signing_code)  
  
- [Palet yönetme](#_core_managing_the_palette)  
  
- [Internet Explorer tarayıcı güvenlik düzeyleri ve denetim davranışı](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 En iyi duruma getirme, açıklandığı gibi ekleyebilirsiniz [ActiveX denetimleri: iyileştirme](../mfc/mfc-activex-controls-optimization.md). Adlar, Özellikler yüklemek için kullanılabilir ve zaman uyumsuz olarak açıklandığı gibi büyük BLOB [Internet'te ActiveX denetimleri](../mfc/activex-controls-on-the-internet.md).  
  
##  <a name="_core_packaging_code_for_downloading"></a> İndirme için kodu paketleme  
 Bu konu hakkında daha fazla bilgi için "Paketleme MFC denetimleri için kullanım Internet üzerinden" (Q167158) Bilgi Bankası makalesine bakın. Bilgi Bankası makalelerini bulabilirsiniz [ http://support.microsoft.com/support ](http://support.microsoft.com/support).  
  
### <a name="the-codebase-tag"></a>CODEBASE etiketi  
 ActiveX denetimlerini kullanarak Web sayfalarında katıştırılmış `<OBJECT>` etiketi. `CODEBASE` Parametresinin `<OBJECT>` etiket denetimi indirileceği konumu belirtir. `CODEBASE` farklı dosya türleri numaradan başarıyla işaret edebilir.  
  
### <a name="using-the-codebase-tag-with-an-ocx-file"></a>CODEBASE etiketi bir OCX dosyası kullanarak  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"  
```  
  
 Bu çözüm yalnızca denetimin .ocx dosya yüklemeleri ve destekleyici DLL'lerin istemci makinede zaten yüklü olmasını gerektirir. Visual C++ denetimler için destek DLL'leri Internet Explorer birlikte çünkü bu Visual C++ ile oluşturulmuş Internet Explorer ve MFC ActiveX denetimleri için çalışır. ActiveX denetimi özellikli olan başka bir Internet tarayıcısı, bu denetim görüntülemek için kullanılırsa, bu çözüm çalışmaz.  
  
### <a name="using-the-codebase-tag-with-an-inf-file"></a>Bir INF dosyası CODEBASE etiketi kullanarak  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 Bir .inf dosyası bir .ocx ve Tamamlayıcı dosyaları yüklenmesini kontrol edecek. Bir .inf dosyası oturum mümkün olmadığı için bu yöntem önerilmez (bkz [kod imzalama](#_core_signing_code) kod imzalama hakkında işaretçileri için).  
  
### <a name="using-the-codebase-tag-with-a-cab-file"></a>CODEBASE etiketi bir CAB dosyası kullanarak  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"  
```  
  
 Dolap dosyalarını MFC kullanmak paket ActiveX denetimleri için önerilen yoldur. MFC ActiveX denetimi dolap dosyasında paketleme ActiveX denetimi ve bağımlı DLL'lerin (örneğin, MFC DLL) denetim yüklemesine dahil edilecek bir .inf dosyası sağlar. Bir CAB dosyası otomatik olarak kullanarak daha hızlı indirme için kodu sıkıştırır. Bileşen yüklemesi için bir .cab dosyası kullanıyorsanız, tek tek her bileşen daha tüm .cab dosyasını imzalamak için daha hızlıdır.  
  
### <a name="creating-cab-files"></a>CAB dosyaları oluşturma  
 Bilgi Bankası makalesi dolap Geliştirme Seti indirebilirsiniz [310618: Microsoft dolap Yazılım Geliştirme Seti](http://go.microsoft.com/fwlink/p/?linkid=148204). Bu Seti'nde dolap dosyalarını oluşturmak için gerekli araçları bulacaksınız.  
  
 Tarafından için dolap dosyası işaret `CODEBASE` ActiveX denetimi .ocx dosya ve onun yükleme denetlemek için bir .inf dosyası içermelidir. Denetim dosyanızın adını belirterek dolap dosyası ve bir .inf dosyası oluşturun. Bu dolap dosyası, sistemde zaten mevcut olabilir bağımlı DLL'lerin içermez. Örneğin, MFC DLL'leri ayrı bir dolap dosyasında paketlenir ve denetleme .inf dosyası tarafından başvurulan.  
  
 CAB dosyasının nasıl oluşturulacağı hakkında daha fazla bilgi için bkz: [bir CAB dosyası oluşturulurken](http://msdn.microsoft.com/en-us/cc52fd09-bdf6-4410-a693-149a308f36a3).  
  
### <a name="the-inf-file"></a>INF dosyası  
 Aşağıdaki örnek, spindial.inf listeleri destekleyici dosyaları ve sürüm bilgileri için MFC Spindial denetimi. MFC DLL'leri için konum Microsoft Web sitesini olduğuna dikkat edin. Mfc42.cab sağlanan ve Microsoft tarafından imzalanmış.  
  
```  
Contents of spindial.inf:  
[mfc42installer]   
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab   
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0  
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0  
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0  
```  
  
### <a name="the-object-tag"></a>\<NESNESİ > etiketi  
 Aşağıdaki örnek kullanarak gösterilmektedir `<OBJECT>` MFC Spindial örnek denetimi paketlemek için etiketi.  
  
```  
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51  
    CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3" 
    CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001"> 
 <PARAM NAME="_Version" VALUE="65536">  
 <PARAM NAME="_ExtentX" VALUE="2646">  
 <PARAM NAME="_ExtentY" VALUE="1323">  
 <PARAM NAME="_StockProps" VALUE="0">  
 <PARAM NAME="NeedlePosition" VALUE="2">  
</OBJECT>  
```  
  
 Bu durumda, iki dosya, spindial.ocx ve spindial.inf spindial.cab içerir. Aşağıdaki komutu dolap dosyası oluşturacak:  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 `-s 6144` Parametresi kod imzalama için dolap alan ayırır.  
  
### <a name="the-version-tag"></a>Sürüm etiketi  
 Burada unutmayın `#Version` tarafından belirtilen denetim uygulandığı bir CAB dosyası ile belirtilen bilgileri `CLASSID` parametresinin `<OBJECT>` etiketi.  
  
 Belirtilen sürüm bağlı olarak, indirme denetiminizin zorlayabilirsiniz. Tam belirtimleri için `OBJECT` etiketi de dahil olmak üzere `CODEBASE` parametresi, bkz: W3C başvurusu.  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> Komut dosyası oluşturma ve başlatma için bir denetim güvenli işaretleme  
 ActiveX denetimleri Web sayfalarında kullanılan kodlama için güvenli ve hatta güvenli olmaları durumunda başlatma için güvenli olarak işaretlenmesi gerekir. Güvenli bir denetim değil disk GÇ gerçekleştirin veya bellek veya bir makine kayıtları doğrudan erişir.  
  
 Denetimleri, kodlama için güvenli ve kayıt defterinden başlatma için güvenli olarak işaretlenebilir. Değiştirme `DllRegisterServer` denetimini komut dosyaları ve kayıt defterinde kalıcılığı için güvenli olarak işaretlemek için aşağıdakilere benzer girdileri eklemek için. Alternatif bir yöntem uygulamaktır `IObjectSafety`.  
  
 Kalıcılığı ve komut dosyası için güvenli olarak işaretlemek denetlemek için GUID (genel benzersiz tanımlayıcı) tanımlayacaksınız. Güvenli bir şekilde Script denetimleri aşağıdakine benzer bir kayıt defteri girdisi içerir:  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Kalıcı verileri güvenli bir şekilde başlatılabilir denetimleri güvenli benzer bir kayıt defteri girişi ile kalıcılığı için işaretlenmiş:  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Aşağıdakine benzer girişler ekleyin (denetiminizin değiştirerek sınıfı kimliği yerine `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) anahtarlarınızı aşağıdaki sınıfı kimliği ile ilişkilendirmek için:  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a> Lisans sorunları  
 Bir Web sayfasında lisanslı bir denetimi kullanmak istiyorsanız, Lisans Sözleşmesi'ni Internet'te kullanımına izin verir ve bir lisans paket dosyası (LPK) oluşturulduğu doğrulamanız gerekir.  
  
 Internet Explorer'ı çalıştıran bilgisayarın denetimini kullanabilmek için lisanslı değilse, lisanslı bir ActiveX denetimi bir HTML sayfasında düzgün yüklemez. Örneğin, lisanslı denetim Visual C++ kullanılarak oluşturuldu, denetimi kullanarak HTML sayfası düzgün burada denetimi oluşturuldu, ancak lisans bilgileri dahil değilse farklı bir bilgisayarda yüklemez bilgisayarda yükleyin.  
  
 Internet Explorer'da lisanslı bir ActiveX denetimi kullanmak için Denetim lisansını izin verdiğini doğrulamak için satıcının lisans sözleşmesi işaretlemeniz gerekir:  
  
-   Yeniden Dağıtım  
  
-   Internet üzerindeki denetiminin kullanımı  
  
-   Codebase parametresi  
  
 Bir HTML sayfasında nonlicensed bir makinede lisanslı denetimi kullanmak için bir lisans paket dosyası (LPK) oluşturmanız gerekir. Çalışma zamanı lisansları lisanslı denetimleri HTML sayfası için LPK dosya içeriyor. Bu dosya LPK_TOOL oluşturulur. ActiveX SDK'sı ile birlikte gelen EXE. Daha fazla bilgi için MSDN Web sitesinde bkz [ http://msdn.microsoft.com ](http://msdn.microsoft.com).  
  
#### <a name="to-create-an-lpk-file"></a>Bir LPK dosyası oluşturmak için  
  
1.  LPK_TOOL çalıştırın. EXE denetimi kullanmak için lisanslı bir bilgisayarda.  
  
2.  İçinde **lisans paketi yazma aracı** iletişim kutusunda **kullanılabilir denetimler** liste kutusu seçme her lisanslı'ı tıklatın ve HTML sayfasında kullanılacak ActiveX denetimini **Ekle**.  
  
3.  Tıklatın **çıkmak & Kaydet** ve LPK dosyası için bir ad yazın. Bu LPK dosyası oluşturun ve uygulamayı kapatın.  
  
#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>Bir HTML sayfasında lisanslı denetim eklemek için  
  
1.  HTML sayfası düzenleyin. HTML sayfasına ekleme bir \<NESNESİ > etiketi diğer önce Lisans Yöneticisi nesnesi için \<NESNESİ > etiketler. Internet Explorer ile yüklenen bir ActiveX denetimi lisans yöneticisidir. Sınıf Kimliğini aşağıda gösterilmiştir. Lisans Yöneticisi'ni nesnesinin LPKPath özelliğini LPK dosyasının adını ve yolunu için ayarlayın. HTML sayfası başına yalnızca bir LPK dosyası olabilir.  
  
 ```  
 <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
 </OBJECT>  
 ```  
  
2.  INSERT \<NESNESİ > Lisans Yöneticisi etiketinden sonra lisanslı denetim için etiket.  
  
     Örneğin, Microsoft maskeli düzenleme denetimi görüntüleyen bir HTML sayfası aşağıda gösterilmiştir. Lisans Yöneticisi denetimidir kimliği ilk sınıfı, ikinci sınıfı için maskeli düzenleme denetimi kimliğidir. Daha önce oluşturduğunuz .lpk dosyanın göreli yolu gösterecek biçimde etiketleri değiştirebilir ve denetlemek için sınıf kimliği de dahil olmak üzere bir nesne etiketi ekleyebilirsiniz.  
  
3.  INSERT \<EMBED > Eklenti NCompass ActiveX kullanıyorsanız LPK dosyanız için öznitelik.  
  
     Diğer denetim görüntülenebilir etkin tarayıcılar etkin — Örneğin, eklenti NCompass ActiveX kullanarak Netscape — eklemeniz gerekir \<EMBED > aşağıda gösterildiği gibi sözdizimi.  
  
 ```  
 <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
 
 <EMBED SRC = "maskedit.LPK">  
 
 </OBJECT>  
 <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
 </OBJECT>  
 ```  
  
 Denetim lisanslama hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: ActiveX denetimini lisanslama](../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
##  <a name="_core_signing_code"></a> Kod imzalama  
 Kod kaynağını belirlemek için kod imzalama tasarlanmıştır ve kod bu yana değişmediğini güvence altına almak için imzalandı. Tarayıcı güvenlik ayarlarına bağlı olarak kod indirilmeden önce kullanıcıların uyarılmak. Kullanıcılar belirli sertifika sahipleri veya uyarısı olmadan yüklenir, bu tarafından imzalanmış servis talebi kod güvenilir şirketler, güven tercih edebilirsiniz. Kod müdahale edilmesini önlemek için dijital olarak imzalanır.  
  
 Denetim güven uyarı iletilerini görüntülemeden otomatik olarak indirilebilir son kodunuzu imzalandığı emin olun. Kod imzalama hakkında ayrıntılar, Authenticode ActiveX SDK'sındaki üzerinde belgelerine bakın ve bkz [bir CAB dosyası imzalama](http://msdn.microsoft.com/en-us/04d8b47a-8f1c-4b54-ab90-730fcdc03747).  
  
 Güven ve tarayıcı güvenlik düzeyi ayarlarına bağlı olarak, bir sertifika imzalama kişi veya şirket tanımlamak için görüntülenebilir. Güvenlik düzeyi none ise veya imzalı denetimin sertifika sahibinin güvenilir ise, bir sertifika görüntülenmez. Bkz: [Internet Explorer tarayıcı güvenlik düzeyleri ve davranışını denetlemeye](#_core_internet_explorer_browser_safety_levels_and_control_behavior) ilişkin ayrıntılar denetiminizi olup indirilir ve görüntülenen bir sertifikayı tarayıcı güvenlik ayarı nasıl belirler.  
  
 Dijital imza garanti kod imzalı bu yana değişmemiştir. Bir karma kod alınır ve sertifikada katıştırılmış. Bu karma daha sonra bir kod İndirildikten sonra ancak çalıştırılmadan önce geçen kod karma ile karşılaştırılır. Verisign gibi şirketler kodunu imzalamak için gereken özel ve genel anahtarlar sağlayabilir. ActiveX SDK'sı MakeCert, sınama sertifikaları oluşturmak için bir yardımcı programı ile birlikte gelir.  
  
##  <a name="_core_managing_the_palette"></a> Palet yönetme  
 Kapsayıcılar palet belirlemek ve bir ortam özelliği olarak kullanılabilir duruma **DISPID_AMBIENT_PALETTE**. Bir kapsayıcı (örneğin, Internet Explorer) tarafından bir sayfadaki tüm ActiveX denetimleri, kendi palet belirlemek için kullanılan bir palet seçer. Bu görüntü titremeyi engeller ve tutarlı bir görünüm sunar.  
  
 Bir denetim kılabilirsiniz `OnAmbientPropertyChange` palet yapılan değişikliklerin bildirimini işlemek için.  
  
 Bir denetim kılabilirsiniz `OnGetColorSet` bir renk paletini çizmek için kümesini dönün. Kapsayıcıları dönüş değeri bir denetim palet uyumlu olup olmadığını belirlemek için kullanın.  
  
 OCX 96 yönergeleri altında bir denetim her zaman arka planda paletini fark gerekir.  
  
 Ortam palette özelliğinden kullanmayın eski kapsayıcıları gönderecek `WM_QUERYNEWPALETTE` ve `WM_PALETTECHANGED` iletileri. Bir denetim kılabilirsiniz `OnQueryNewPalette` ve `OnPaletteChanged` bu iletileri işlemek için.  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer tarayıcı güvenlik düzeyleri ve denetim davranışı  
 Bir tarayıcı için güvenlik düzeyi, kullanıcı tarafından yapılandırılabilir seçenekleri vardır. Web sayfaları bir kullanıcının bilgisayarına zarar etkin içerik içerdiğinden tarayıcılar için güvenlik düzeyi seçeneklerini seçmek verin. Bir tarayıcı güvenlik düzeyleri uygulayan şekilde, bağlı olarak bir denetim hiç yüklenmedi veya bir sertifika veya çalışma zamanında denetimini karşıdan gerekip gerekmediğini seçmesine izin vermek için bir uyarı iletisi görüntülenir. Internet Explorer ActiveX denetimlerinde yüksek, Orta ve düşük güvenilirlik düzeylerinin altındaki davranışını aşağıda listelenmiştir.  
  
### <a name="high-safety-mode"></a>Yüksek güvenlik modu  
  
-   İmzasız denetimlerini yüklenmeyecektir.  
  
-   İmzalanmış denetimler, bir sertifika görüntülenir, güvenilmeyen varsa (bir kullanıcı her zaman bu sertifika sahibinin koddan şu andan itibaren güven için bir seçenek seçebilirsiniz).  
  
-   Yalnızca güvenli olarak işaretlenmiş denetimleri kalıcı veri ve/veya sahip kodlanabilir.  
  
### <a name="medium-safety-mode"></a>Orta güvenlik modu  
  
-   İmzasız denetimlerini yüklemeden önce bir uyarı görüntüler.  
  
-   İmzalanmış denetimler güvenilmeyen bir sertifika görüntülenir.  
  
-   Denetimleri güvenli olarak işaretlenmemiş bir uyarı görüntüler.  
  
### <a name="low-safety-mode"></a>Düşük güvenlik modu  
  
-   Denetimleri uyarmadan indirilir.  
  
-   Komut dosyası ve kalıcılığı uyarmadan oluşur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Internet programlama görevleri](../mfc/mfc-internet-programming-tasks.md)   
 [MFC Internet Programlama temelleri](../mfc/mfc-internet-programming-basics.md)   
 [MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

