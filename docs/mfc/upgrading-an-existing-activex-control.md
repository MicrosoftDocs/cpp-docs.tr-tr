---
title: Varolan Bir ActiveX Denetimini Güncelleştirme
ms.date: 09/12/2018
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
ms.openlocfilehash: 06c39240d3718f6fbaa15b46abeb8ac9132b5945
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510865"
---
# <a name="upgrading-an-existing-activex-control"></a>Varolan Bir ActiveX Denetimini Güncelleştirme

Mevcut ActiveX denetimleri (eski adıyla OLE denetimleri), Internet üzerinde değişiklik yapılmadan kullanılabilir. Ancak, performansını geliştirmek için denetimleri değiştirmek isteyebilirsiniz.

> [!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Denetiminizi bir Web sayfasında kullanırken, ek hususlar vardır. . Ocx dosyası ve tüm destekleyici dosyalar hedef makinede olmalı veya Internet üzerinden indirilmelidir. Bu, kod boyutunu ve indirme süresini önemli bir şekilde oluşturur. İndirilenler imzalı bir. cab dosyasında paketlenebilir. Denetiminizi betik için güvenli olarak işaretleyebilir ve başlatma için güvenli olarak işaretleyebilirsiniz.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Indirme için paketleme kodu](#_core_packaging_code_for_downloading)

- [Bir denetimi betik oluşturma ve başlatma için güvenli olarak işaretleme](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [Lisanslama sorunları](#_core_licensing_issues)

- [İmzalama kodu](#_core_signing_code)

- [Paleti yönetme](#_core_managing_the_palette)

- [Internet Explorer tarayıcı güvenlik düzeyleri ve denetim davranışı](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

Ayrıca, [ActiveX denetimlerinde açıklandığı gibi iyileştirmeler da ekleyebilirsiniz: İyileştirme](../mfc/mfc-activex-controls-optimization.md). Bilinen adlar, [Internet 'Teki ActiveX denetimlerinde](../mfc/activex-controls-on-the-internet.md)açıklandığı gibi, özellikleri ve büyük Blobları zaman uyumsuz olarak indirmek için kullanılabilir.

##  <a name="_core_packaging_code_for_downloading"></a>Indirme için paketleme kodu

Bu konu hakkında daha fazla bilgi için bkz. [paketleme ActiveX denetimleri](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29).

### <a name="the-codebase-tag"></a>CODEBASE etiketi

ActiveX denetimleri `<OBJECT>` etiketi kullanılarak Web sayfalarına katıştırılır. `<OBJECT>` Etiketin parametresi ,denetimin`CODEBASE` indirileceği konumu belirtir. `CODEBASE`, bir dizi farklı dosya türünü başarıyla işaret edebilir.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>Bir OCX dosyası ile CODEBASE etiketini kullanma

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

Bu çözüm yalnızca denetimin. ocx dosyasını indirir ve istemci makinesine zaten yüklü olan destekleyen dll 'Leri gerektirir. Internet Explorer görsel C++ denetimler Için destekleme dll 'leriyle birlikte geldiği için, bu C++, Visual ile oluşturulan Internet Explorer ve MFC ActiveX denetimleri için de çalışır. Bu denetimi görüntülemek için ActiveX denetimi özellikli başka bir Internet tarayıcısı kullanılırsa bu çözüm çalışmaz.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>KOD temelı etiketini bir INF dosyası ile kullanma

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

Bir. inf dosyası, bir. ocx ve destekleyici dosyalarının yüklenmesini denetler. Bu yöntem, bir. inf dosyasını imzalamak mümkün olmadığından önerilmez (bkz. kod imzalama işaretçileri için [Imzalama kodu](#_core_signing_code) ).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>KOD temelı etiketini bir CAB dosyası ile kullanma

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

Dolap dosyaları, MFC kullanan ActiveX denetimlerini paketlemek için önerilen yoldur. Bir dolap dosyasında MFC ActiveX denetimi paketleme, ActiveX denetiminin ve bağımlı dll 'lerin (MFC DLL 'Leri gibi) yüklenmesine yönelik bir. inf dosyasının eklenmesini sağlar. CAB dosyası kullanmak, daha hızlı indirme için kodu otomatik olarak sıkıştırır. Bileşen indirme için bir. cab dosyası kullanıyorsanız, tüm. cab dosyasını tek bir bileşenden imzalamanız daha hızlıdır.

### <a name="creating-cab-files"></a>CAB dosyaları oluşturuluyor

Dolap dosyalarını oluşturmaya yönelik araçlar artık [Windows 10 SDK 'sının](https://dev.windows.com/downloads/windows-10-sdk)bir parçasıdır.

Tarafından `CODEBASE` işaret edilen dolap dosyası, ActiveX denetiminizin. ocx dosyasını ve yüklemesini denetlemek için bir. inf dosyasını içermelidir. Denetim dosyanızın adını ve bir. inf dosyasını belirterek dolap dosyasını oluşturursunuz. Bu dolap dosyasında sistemde zaten mevcut olabilecek bağımlı dll 'Leri eklemeyin. Örneğin, MFC DLL 'Leri ayrı bir dolap dosyasında paketlenir ve denetleyen. inf dosyası tarafından başvurulur.

CAB dosyası oluşturma hakkında ayrıntılı bilgi için bkz. [cab dosyası oluşturma](/windows/win32/devnotes/cabinet-api-functions).

### <a name="the-inf-file"></a>INF dosyası

Aşağıdaki örnek, spındial. inf, desteklenen dosyaları ve MFC Spındial denetimi için gereken sürüm bilgilerini listeler. MFC DLL 'Lerinin bir Microsoft Web sitesi olduğunu unutmayın. Mfc42. cab, Microsoft tarafından sağlanır ve imzalanır.

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

### <a name="the-object-tag"></a>\<Nesne > etiketi

Aşağıdaki örnek, MFC spındial örnek denetimini paketlemek için `<OBJECT>` etiketinin kullanımını gösterir.

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

Bu durumda, spındial. cab dosyası, spındial. ocx ve spındial. inf olmak üzere iki dosya içerir. Aşağıdaki komut, dolap dosyasını oluşturacak:

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

`-s 6144` Parametresi kod imzalama için dolapta alan ayırır.

### <a name="the-version-tag"></a>Sürüm etiketi

Buraya `#Version` , bir cab dosyası ile belirtilen bilgilerin, `<OBJECT>` etiketin *ClassID* parametresi tarafından belirtilen denetime uygulandığını unutmayın.

Belirtilen sürüme bağlı olarak, denetiminizin indirilmesini zorla indirebilirsiniz. *Kod temeli* parametresi dahil olmak `OBJECT` üzere etiketin tüm özellikleri için bkz. W3C başvurusu.

##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>Bir denetimi betik oluşturma ve başlatma için güvenli olarak işaretleme

Web sayfalarında kullanılan ActiveX denetimleri, komut dosyası oluşturma için güvenli olarak işaretlenmelidir ve gerçek güvende olmaları durumunda başlatma için güvenlidir. Güvenli denetim, disk GÇ gerçekleştirmez veya bir makinenin belleğine veya kayıt defterlerine doğrudan erişemez.

Denetimler, komut dosyası ve kayıt defteri aracılığıyla başlatılması için güvenli olarak işaretlenebilir. Denetim `DllRegisterServer` , kayıt defterinde betik oluşturma ve kalıcılık için güvenli olarak işaretlemek üzere aşağıdakine benzer girdileri eklemek için değiştirin. Alternatif bir yöntem uygulamaktır `IObjectSafety`.

Komut dosyası oluşturma ve kalıcılık için güvenli olarak işaretlemek üzere denetiminizin GUID 'Leri (genel benzersiz tanımlayıcılar) tanımlayacaksınız. Güvenli bir şekilde komut dosyasıyla kullanılabilecek denetimler aşağıdakine benzer bir kayıt defteri girişi içerir:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

Kalıcı verilerden güvenle başlatılan denetimler şuna benzer bir kayıt defteri girdisiyle Kalıcılık için güvenli olarak işaretlenir:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

Anahtarlarınızı aşağıdaki sınıf kimliğiyle ilişkilendirmek için aşağıdakine benzer girdileri ekleyin (denetiminizin sınıf kimliğini `{06889605-B8D0-101A-91F1-00608CEAD5B3}`yerine).

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

##  <a name="_core_licensing_issues"></a>Lisanslama sorunları

Bir Web sayfasında lisanslı bir denetim kullanmak istiyorsanız, lisans sözleşmesinin Internet 'te kullanılmasına izin verdiğini ve bunun için bir lisans paketi dosyası (LPK) oluşturup oluşturmadığını doğrulamanız gerekir.

Internet Explorer çalıştıran bilgisayarın denetimi kullanmak üzere lisansı yoksa, bir HTML sayfasında lisanslı bir ActiveX denetimi düzgün yüklenmez. Örneğin, lisanslı bir denetim görsel C++kullanılarak oluşturulduysa, denetımı kullanan html sayfası, denetimin oluşturulduğu bilgisayara düzgün şekilde yüklenir, ancak lisanslama bilgileri dahil edilmedikleri takdirde farklı bir bilgisayara yüklenmeyecektir.

Internet Explorer 'da lisanslı bir ActiveX denetimini kullanmak için, denetimin lisansının izin verdiğinden emin olmak üzere satıcının lisans sözleşmesini denetlemeniz gerekir:

- Yeniden Dağıtım

- Internet 'te denetim kullanımı

- CodeBase parametresinin kullanımı

Lisanslı olmayan bir makinede bir HTML sayfasında lisanslı bir denetim kullanmak için, bir lisans paketi dosyası (LPK) oluşturmanız gerekir. LPK dosyası, HTML sayfasındaki lisanslı denetimlerin çalışma zamanı lisanslarını içerir. Bu dosya LPK_TOOL aracılığıyla oluşturulur. ActiveX SDK ile birlikte gelen EXE.

#### <a name="to-create-an-lpk-file"></a>Bir LPK dosyası oluşturmak için

1. LPK_TOOL çalıştırın. EXE ' yi kullanarak denetleyin.

1. **Lisans paketi yazma aracı** iletişim kutusunda, **kullanılabilir denetimler** liste kutusunda, HTML sayfasında kullanılacak olan her lisanslı ActiveX denetimini seçin ve **Ekle**' ye tıklayın.

1. **Kaydet & çıkış** ' a tıklayın ve lpk dosyası için bir ad yazın. Bu, LPK dosyasını oluşturur ve uygulamayı kapatır.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>Lisanslı bir denetimi HTML sayfasına eklemek için

1. HTML sayfanızı düzenleyin. HTML sayfasında, diğer \< \<herhangi bir nesne > etiketini kullanmadan önce, Lisans Yöneticisi nesnesi için bir nesne > etiketi ekleyin. Lisans Yöneticisi, Internet Explorer ile yüklenen bir ActiveX denetimidir. Sınıf KIMLIĞI aşağıda gösterilmiştir. Lisans Yöneticisi nesnesinin LPKPath özelliğini LPK dosyasının yolu ve adı olarak ayarlayın. HTML sayfası başına yalnızca bir LPK dosyasına sahip olabilirsiniz.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. Lisans Yöneticisi etiketinden sonra lisanslı denetiminizin Nesne>etiketiniekleyin.\<

   Örneğin, Microsoft maskelenmiş düzenleme denetimini görüntüleyen bir HTML sayfası aşağıda gösterilmiştir. İlk sınıf KIMLIĞI, Lisans Yöneticisi denetimine yöneliktir, ikinci sınıf KIMLIĞI maskelenmiş düzenleme denetimine yöneliktir. Etiketleri, daha önce oluşturduğunuz. lpk dosyasının göreli yolunu işaret etmek üzere değiştirin ve denetiminizin sınıf KIMLIĞINI içeren bir nesne etiketi ekleyin.

1. Npusula ActiveX eklentisini kullanıyorsanız, LPK dosyanız için ekleme>özniteliğiniekleyin.\<

   Denetiminiz, diğer etkin etkin tarayıcılarda görüntülenebilir — Örneğin, npusula ActiveX eklentisini kullanan Netscape — ekleme > sözdizimini aşağıda gösterildiği gibi eklemeniz \<gerekir.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

Denetim lisanslama hakkında daha fazla bilgi için bkz [. ActiveX denetimleri: ActiveX denetimini](../mfc/mfc-activex-controls-licensing-an-activex-control.md)lisanslama.

##  <a name="_core_signing_code"></a>İmzalama kodu

Kod imzalama kod kaynağını belirlemek ve kodun imzalanmasından bu yana değiştirilmediğinden emin olmak için tasarlanmıştır. Tarayıcı güvenlik ayarlarına bağlı olarak, kullanıcılar Kod indirilmeden önce uyarı verebilir. Kullanıcılar belirli sertifika sahiplerine veya şirketlere güvenmeyi seçebilir ve bu durum, güvenilir tarafından imzalanan kodun uyarı olmadan indirileceği durumdur. Değişiklik yapmaktan kaçınmak için kod dijital olarak imzalandı.

Denetiminizin, güven uyarı iletileri görüntülenmeden otomatik olarak indirilebilmesi için son kodunuzun imzalandığından emin olun. Kodu imzalama hakkında daha fazla bilgi için, ActiveX SDK 'da Authenticode ile ilgili belgelere bakın ve [BIR cab dosyasını imzalama](/windows/win32/devnotes/cabinet-api-functions)bölümüne bakın.

Güven ve tarayıcı güvenlik düzeyi ayarlarına bağlı olarak, imzalayan kişiyi veya şirketi belirlemek için bir sertifika görüntülenebilir. Güvenlik düzeyi none ise veya imzalanmış denetimin sertifika sahibi güvenilirse, bir sertifika gösterilmeyecektir. Tarayıcı güvenliği ayarının denetiminizin indirilip indirilmediğini ve bir sertifikanın görüntülendiğini nasıl belirleyeceğini öğrenmek için bkz. [Internet Explorer tarayıcı güvenlik düzeyleri ve denetim davranışı](#_core_internet_explorer_browser_safety_levels_and_control_behavior) .

Dijital imzalama kodu, imzalandığından bu yana değiştirilmiyor. Kod karması, sertifikaya alınır ve sertifikayı katıştırılır. Bu karma daha sonra kod indirildikten sonra, ancak çalıştırılmadan önce alınan kodun karması ile karşılaştırılır. VeriSign gibi şirketler, kodu imzalamak için gereken özel ve ortak anahtarları sağlayabilir. ActiveX SDK, test sertifikaları oluşturmaya yönelik bir yardımcı program olan MakeCert ile birlikte gelir.

##  <a name="_core_managing_the_palette"></a>Paleti yönetme

Kapsayıcılar, paleti ve **DISPID_AMBIENT_PALETTE**ortam özelliği olarak kullanılabilir hale getirir. Bir kapsayıcı (örneğin, Internet Explorer) kendi paletini belirleyebilmek için bir sayfadaki tüm ActiveX denetimleri tarafından kullanılan bir paleti seçer. Bu, ekran titreşmesini engeller ve tutarlı bir görünüm sunar.

Bir denetim, paletteki `OnAmbientPropertyChange` değişikliklerin bildirimini işlemek için geçersiz kılınabilir.

Bir denetim, paleti `OnGetColorSet` çizmek üzere bir renk kümesi döndürmek için geçersiz kılınabilir. Kapsayıcılar, bir denetimin palet duyarlı olup olmadığını anlamak için dönüş değerini kullanır.

OCX 96 yönergeleri altında, bir denetim her zaman arka planda paletini sağlamalıdır.

Çevresel palet özelliğini kullanmayan eski kapsayıcılar, WM_QUERYNEWPALETTE ve WM_PALETTECHANGED iletilerini gönderir. Bir denetim, bu `OnQueryNewPalette` iletileri `OnPaletteChanged` geçersiz kılabilir ve işleyebilir.

##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>Internet Explorer tarayıcı güvenlik düzeyleri ve denetim davranışı

Tarayıcı, Kullanıcı tarafından yapılandırılabilen güvenlik düzeyi seçeneklerine sahiptir. Web sayfaları, bir kullanıcının bilgisayarına zarar verebilecek etkin içerikleri içerebildiğinden, tarayıcılar kullanıcının güvenlik düzeyi seçeneklerini seçmesine izin verir. Tarayıcının güvenlik düzeylerini uygulayan yönteme bağlı olarak, bir denetim hiç indirilemeyebilir veya kullanıcının denetimin indirilip indirilmeyeceğini, çalışma zamanında seçmesine izin vermek için bir sertifika veya uyarı iletisi görüntüler. Internet Explorer 'da yüksek, orta ve düşük güvenlik seviyeleri altında ActiveX denetimlerinin davranışı aşağıda listelenmiştir.

### <a name="high-safety-mode"></a>Yüksek güvenlik modu

- İmzasız denetimler indirilmez.

- İmzalı denetimler, güvenilir değilse bir sertifika görüntüler (Kullanıcı bu sertifika sahibinden her zaman koda her zaman güvenmek için bir seçenek seçebilir).

- Yalnızca güvenli olarak işaretlenen denetimlerin kalıcı verileri olur ve/veya komut dosyası oluşturulabilir.

### <a name="medium-safety-mode"></a>Orta düzey güvenlik modu

- İmzasız denetimler, indirilmeden önce bir uyarı görüntüler.

- İmzalı denetimler, güvenilir değilse bir sertifika görüntüler.

- Güvenli olarak işaretlenmemiş denetimler, bir uyarı görüntüler.

### <a name="low-safety-mode"></a>Düşük güvenlik modu

- Denetimler uyarı vermeden indirilir.

- Betik oluşturma ve kalıcılık uyarı olmadan oluşur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Internet Programlama Görevleri](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC Internet Programlama Temelleri](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX Denetimleri: ActiveX Denetimi Lisanslama](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
