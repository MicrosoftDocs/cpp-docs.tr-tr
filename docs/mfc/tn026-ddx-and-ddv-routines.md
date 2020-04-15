---
title: 'TN026: DDX ve DDV Rutinleri'
ms.date: 06/28/2018
f1_keywords:
- DDX
- DDV
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
ms.openlocfilehash: 711d433b51ca09836f372d09a11f86c28b82cce6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370343"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX ve DDV Rutinleri

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, iletişim veri alışverişi (DDX) ve iletişim veri doğrulama (DDV) mimarisini açıklar. Ayrıca, bir DDX_ veya DDV_ yordamı nasıl yazdığınızı ve ClassWizard'ı yordamlarınızı kullanmak üzere nasıl genişletebileceğinizi de açıklar.

## <a name="overview-of-dialog-data-exchange"></a>İletişim Veri Alışverişine Genel Bakış

Tüm iletişim veri fonksiyonları C++ kodu ile yapılır. Özel kaynaklar veya sihirli makrolar yoktur. Mekanizmanın kalbi, iletişim veri alışverişi ve doğrulama yapan her iletişim sınıfında geçersiz kılınan sanal bir işlevdir. Her zaman bu formda bulunur:

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

Özel biçimAFX açıklamaları ClassWizard'ın bu işlev içindeki kodu bulmasına ve yönetmesine olanak sağlar. ClassWizard ile uyumlu olmayan kod, özel biçim açıklamalarının dışına yerleştirilmelidir.

Yukarıdaki örnekte, \<data_exchange_function_call> şeklindedir:

```cpp
DDX_Custom(pDX, nIDC, field);
```

ve \<data_validation_function_call> isteğe bağlıdır ve şeklindedir:

```cpp
DDV_Custom(pDX, field, ...);
```

Her `DoDataExchange` işleve birden fazla DDX_/DDV_ çifti dahil edilebilir.

MFC ile sağlanan tüm iletişim veri alışverişi yordamlarının ve iletişim veri doğrulama yordamlarının listesi için 'afxdd_.h' bölümüne bakın.

İletişim verileri sadece şudur: sınıftaki `CMyDialog` üye verileri. Bir yapı da veya benzeri bir şeyde depolanmaz.

## <a name="notes"></a>Notlar

Buna "iletişim verileri" dememize rağmen, tüm özellikler `CWnd` yalnızca iletişim sahiplerinden türetilen herhangi bir sınıfta kullanılabilir ve bunlarla sınırlı değildir.

Verilerin ilk değerleri standart C++ oluşturucusunda, genellikle `//{{AFX_DATA_INIT` bir `//}}AFX_DATA_INIT` blokta ve yorumlarda ayarlanır.

`CWnd::UpdateData`için çağrı etrafında başlatma ve hata işleme yapan `DoDataExchange`işlemdir.

Veri alışverişi ve doğrulama gerçekleştirmek için istediğiniz zaman arayabilirsiniz. `CWnd::UpdateData` Varsayılan `UpdateData`olarak (TRUE) varsayılan `CDialog::OnOK` işleyici `UpdateData`olarak adlandırılır ve (FALSE) varsayılan `CDialog::OnInitDialog`olarak çağrılır.

DDV_ rutin hemen bu *alan*için DDX_ rutin takip etmelidir.

## <a name="how-does-it-work"></a>Nasıl Çalışır?

İletişim verilerini kullanmak için aşağıdakileri anlamanız gerekmez. Ancak, bunun perde arkasında nasıl çalıştığını anlamak, kendi değişim veya doğrulama yordamınızı yazmanıza yardımcı olacaktır.

`DoDataExchange` Üye işlev üye işlevine `Serialize` çok benzer - sınıftaki üye verilerden /dış formdan (bu durumda bir iletişim kutusunda denetimler) veri almaktan veya ayarlamaktan sorumludur. *pDX* parametresi veri alışverişi yapmak için bağlamdır `CArchive` ve `CObject::Serialize`parametreye benzer. *pDX* (bir `CDataExchange` nesne) çok benzer `CArchive` bir yön bayrağı vardır bir yön bayrağı vardır:

- Eğer, `!m_bSaveAndValidate`daha sonra denetimlere veri durumu yükleyin.

- Eğer, `m_bSaveAndValidate`daha sonra denetimlerden veri durumunu ayarlayın.

Doğrulama yalnızca ayarlandığında `m_bSaveAndValidate` oluşur. Değeri `m_bSaveAndValidate` BOOL parametresi tarafından `CWnd::UpdateData`belirlenir.

Diğer üç ilginç `CDataExchange` üye vardır:

- `m_pDlgWnd`: Denetimleri içeren pencere (genellikle bir iletişim kutusu). Bu, DDX_ ve DDV_ genel işlevleri arayanların her DDX/DDV yordamına 'bu' geçmek zorunda kalmalarını önlemek içindir.

- `PrepareCtrl`ve `PrepareEditCtrl`: Veri alışverişi için bir iletişim denetimi hazırlar. Doğrulama başarısız olursa odağı ayarlamak için bu denetimin tutamacını depolar. `PrepareCtrl`olmayan edit denetimleri için `PrepareEditCtrl` kullanılır ve denetimleri edin için kullanılır.

- `Fail`: Kullanıcıyı giriş hatasıkonusunda uyaran bir ileti kutusu getirdikten sonra çağrılır. Bu yordam, odağı son denetime geri yükleyecek (son arama `PrepareCtrl` veya) `PrepareEditCtrl`ve bir özel durum atacaktır. Bu üye işlev hem DDX_ hem de DDV_ yordamlarından çağrılabilir.

## <a name="user-extensions"></a>Kullanıcı Uzantıları

Varsayılan DDX/DDV mekanizmasını genişletmenin birkaç yolu vardır. Şunları yapabilirsiniz:

- Yeni veri türleri ekleyin.

    ```cpp
    CTime
    ```

- Yeni değişim yordamları ekleyin (DDX_).

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- Yeni doğrulama yordamları ekleyin (DDV_).

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- Rasgele ifadeleri doğrulama yordamlarına geçirin.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > Bu tür rasgele ifadeler ClassWizard tarafından düzenlenemez ve bu nedenle özel biçim açıklamaları (//{{AFX_DATA_MAP(CMyClass)) dışına taşınmalıdır.

Üye `DoDialogExchange` işlevin, karışık değişim ve doğrulama işlevi çağrıları içeren koşullu veya diğer geçerli C++ deyimlerini içermesini sorun.

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> Yukarıda gösterildiği gibi, bu tür kod ClassWizard tarafından düzenlenemez ve yalnızca özel biçim açıklamaları dışında kullanılmalıdır.

## <a name="classwizard-support"></a>ClassWizard Desteği

ClassWizard, kendi DDX_ ve DDV_ yordamlarınızı ClassWizard kullanıcı arabirimine entegre etmenize izin vererek DDX/DDV özelleştirmelerinin bir alt kümesini destekler. Bunu yapmak, yalnızca belirli DDX ve DDV yordamlarını bir projede veya birçok projede yeniden kullanmayı planlıyorsanız yararlı dır.

Bunu yapmak için, özel girişler DDX yapılır. CLW (Visual C++'ın önceki sürümleri bu bilgileri APSTUDIO'da depolatmilmiştir. INI) veya projenizin . CLW dosyası. Özel girişler projenizin [Genel Bilgi] bölümüne girilebilir. CLW dosyası veya DDX[ExtraDDX] bölümünde. \Program Files\Microsoft Visual Studio\Visual C++\bin dizinindeki CLW dosyası. DDX'i oluşturmanız gerekebilir. ZATEN yoksa CLW dosyası. Özel DDX_/DDV_ yordamlarını yalnızca belirli bir projede kullanmayı planlıyorsanız, girişleri projenizin [Genel Bilgi] bölümüne ekleyin. Bunun yerine CLW dosyası. Yordamları birçok projede kullanmayı planlıyorsanız, girişleri DDX'in [ExtraDDX] bölümüne ekleyin. CLW' den.

Bu özel girişlerin genel biçimi:

> EkstraDDXCount=*n*

*nerede n* ExtraDDX sayısınedir? takip etmek için satırlar, form

> ExtraDDX?=*tuşları*; *vb tuşları*; *istemi*; *türü*; *initValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

Nerede? tanımlanan listede hangi *n* DDX türünü gösteren bir sayı 1 - n'dir.

Her alan bir ';' karakteri ile sınırlandırılır. Alanlar ve amaçları aşağıda açıklanmıştır.

- *Anahtar*

  Bu değişken türünü denetleyen iletişim kutusunugösteren tek karakter listesi.

  |Karakter|İzin verilen denetim|
  |-|-|
  E | düzenle
  C | iki durumlu onay kutusu
  c | üç durumlu onay kutusu
  R | bir gruptaki ilk radyo düğmesi
  L | sıralanmış olmayan liste kutusu
  l | sıralanmış liste kutusu
  M | açılan kutu (öğeyi edit ile)
  N | sıralanmış olmayan bırakma listesi
  n | sıralanmış bırakma listesi
  1 | DDX eklentisi listenin başına eklenecekse (varsayılan kuyruk eklenir) Bu genellikle 'Denetim' özelliğini aktaran DDX yordamları için kullanılır.

- *vb tuşları*

  Bu alan yalnızca VBX kontrolleri için 16 bit üründe kullanılır (VBX kontrolleri 32 bit üründe desteklenmez)

- *Istemi*

  Özellik açılan kutusuna yerleştirilecek dize (tırnak işareti yok)

- *Türü*

  Üstbilgi dosyasına yatacak tür için tek tanımlayıcı. Yukarıdaki DDX_Time örneğimizde, bu CTime olarak ayarlanır.

- *vb tuşları*

  Bu sürümde kullanılmaz ve her zaman boş olmalıdır

- *initValue*

  İlk değer — 0 veya boş. Boşsa, uygulama dosyasının //{{AFX_DATA_INIT bölümüne hiçbir başlatma satırı yazılmaz. Boş bir giriş, doğru başlatmayı garanti `CString`eden `CTime`oluşturuculara sahip C++ nesneleri (, , vb. gibi) için kullanılmalıdır.

- *DDX_Proc*

  DDX_ yordamı için tek tanımlayıcı. C++ işlev adı "DDX_" ile başlamalı, ancak DDX_Proc \<> tanımlayıcıya "DDX_" eklemeyin. Yukarıdaki örnekte, \<> DDX_Proc Zaman olacaktır. ClassWizard {{AFX_DATA_MAP bölümündeki uygulama dosyasına işlev çağrısı yazdığında, bu adı DDX_ ekler ve böylece DDX_Time'a gelir.

- *Yorum*

  Bu DDX ile değişken için iletişim kutusunda göstermek için açıklama. İstediğini istediğiniz metni buraya yerleştirin ve genellikle DDX/DDV çifti tarafından gerçekleştirilen işlemi açıklayan bir şey sağlayın.

- *DDV_Proc*

  Girişin DDV kısmı isteğe bağlıdır. Tüm DDX yordamları karşılık gelen DDV yordamları vardır. Genellikle, doğrulama aşamasını aktarımın ayrılmaz bir parçası olarak eklemek daha uygundur. ClassWizard herhangi bir parametre olmadan DDV yordamları desteklemez, çünkü DDV yordamı herhangi bir parametre gerektirmez, bu genellikle böyledir.

- *Arg*

  DDV_ yordamı için tek tanımlayıcı. C++ işlev adı "DDV_" ile başlamalı, ancak DDX_Proc \<> tanımlayıcıya "DDX_" eklememelidir.

  *arg* 1 veya 2 DDV args takip eder:

  - *promptN*

      Dize, edit öğesinin üzerine yerleştirmek için (hızlandırıcı için &).

  - *fmtN*

      Arg türü için biçim karakteri, biri:

      |Karakter|Tür|
      |-|-|
      |d | int|
      |u | unsigned int|
      |D | uzun int (yani, uzun)|
      |U | uzun imzasız (yani, DWORD)|
      |f | float|
      |F | double|
      |s | string|

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
