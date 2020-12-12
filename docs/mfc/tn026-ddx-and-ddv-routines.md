---
description: 'Daha fazla bilgi edinin: TN026: DDX ve DDV yordamları'
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
ms.openlocfilehash: 1e5c8d3679b7e91ad7f356c1e6f6badc61cdd46f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215709"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX ve DDV Rutinleri

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta iletişim kutusu veri değişimi (DDX) ve iletişim verisi doğrulama (DDV) mimarisi açıklanmaktadır. Ayrıca, bir DDX_ veya DDV_ yordamının nasıl yazılacağını ve kendi yordamlarınızı kullanmak için ClassWizard 'ı nasıl genişletebileceğinizi açıklar.

## <a name="overview-of-dialog-data-exchange"></a>Iletişim kutusu veri değişimine genel bakış

Tüm iletişim kutusu veri işlevleri C++ kodu ile yapılır. Özel kaynak veya sihirli makrolar yoktur. Mekanizmanın kalp, iletişim kutusu veri değişimi ve doğrulaması yapan her iletişim kutusunda geçersiz kılınan bir sanal işlevdir. Bu formda her zaman bulunur:

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

Özel biçim AFX açıklamaları ClassWizard 'ın bu işlev içindeki kodu bulmasını ve düzenlemesini sağlar. ClassWizard ile uyumlu olmayan kod, özel biçim açıklamalarının dışına yerleştirilmelidir.

Yukarıdaki örnekte, \<data_exchange_function_call> şu biçimdedir:

```cpp
DDX_Custom(pDX, nIDC, field);
```

ve \<data_validation_function_call> isteğe bağlıdır ve şu biçimdedir:

```cpp
DDV_Custom(pDX, field, ...);
```

Her işlevde birden fazla DDX_/DDV_ çifti bulunabilir `DoDataExchange` .

MFC ile birlikte sunulan tüm iletişim kutusu veri değişimi yordamları ve iletişim kutusu veri doğrulama yordamlarının listesi için bkz. ' afxdd_. h '.

İletişim kutusu verileri yalnızca şu şekilde yapılır: sınıftaki üye verileri `CMyDialog` . Bir yapıda veya benzer bir şekilde depolanmaz.

## <a name="notes"></a>Notlar

Bu "iletişim kutusu verilerini" çağırdığımızda, tüm özellikler, ' den türetilen herhangi bir sınıfta kullanılabilir `CWnd` ve yalnızca iletişim kutusuyla sınırlı değildir.

İlk veri değerleri standart C++ oluşturucusunda, genellikle ve açıklamaları olan bir blokta ayarlanır `//{{AFX_DATA_INIT` `//}}AFX_DATA_INIT` .

`CWnd::UpdateData` , başlatma ve çağrı çevresinde hata işleme yapan işlemdir `DoDataExchange` .

`CWnd::UpdateData`Veri değişimi ve doğrulama gerçekleştirmek için dilediğiniz zaman çağrı yapabilirsiniz. Varsayılan olarak `UpdateData` (true) varsayılan `CDialog::OnOK` işleyicide çağrılır ve `UpdateData` (false) varsayılan olarak çağırılır `CDialog::OnInitDialog` .

DDV_ yordamı, bu *alanın* ddx_ yordamını hemen izlemelidir.

## <a name="how-does-it-work"></a>Nasıl çalışır?

İletişim kutusu verilerini kullanmak için aşağıdakileri anlamanız gerekmez. Bununla birlikte, bunun arka planda nasıl çalıştığını anlamak kendi Exchange veya doğrulama yordamınıza yazmanızı sağlamanıza yardımcı olur.

`DoDataExchange`Üye işlevi, üye işlevi için çok benzer `Serialize` -bir dış formdan (Bu durumda, bir iletişim kutusundaki denetimlerde), sınıftaki üye verilerinden/öğesinden veri alma veya sunucudan veri ayarlamaktan sorumludur. *PDX* parametresi, veri değişimi yapma bağlamıdır ve `CArchive` parametresine benzerdir `CObject::Serialize` . *PDX* (bir `CDataExchange` nesne) yön bayrağına benzer bir yön bayrağına sahiptir `CArchive` :

- `!m_bSaveAndValidate`Daha sonra veri durumunu denetimlere yükleyin.

- `m_bSaveAndValidate`Daha sonra, veri durumunu denetimlerden ayarlayın.

Doğrulama yalnızca ayarlandığında oluşur `m_bSaveAndValidate` . Değeri `m_bSaveAndValidate` bool parametresi tarafından belirlenir `CWnd::UpdateData` .

İlginç üç farklı üye vardır `CDataExchange` :

- `m_pDlgWnd`: Denetimleri içeren pencere (genellikle bir iletişim kutusu). Bunun nedeni, DDX_ çağıranların ve DDV_ genel işlevlerin ' this ' öğesini her DDX/DDV yordamına geçmesini önler.

- `PrepareCtrl`ve `PrepareEditCtrl` : veri değişimi için bir iletişim denetimi hazırlar. Doğrulama başarısız olursa odağı ayarlamak için bu denetimin tanıtıcısını depolar. `PrepareCtrl` , düzenleme olmayan denetimler için kullanılır ve `PrepareEditCtrl` düzenleme denetimleri için kullanılır.

- `Fail`: Kullanıcıdan giriş hatasına uyarı eden bir ileti kutusu gönderdikten sonra çağırılır. Bu yordam, odağı son denetime geri yükler (veya öğesine yapılan son çağrı `PrepareCtrl` `PrepareEditCtrl` ) ve bir özel durum oluşturur. Bu üye işlevi, hem DDX_ hem de DDV_ yordamlarından çağrılabilir.

## <a name="user-extensions"></a>Kullanıcı Uzantıları

Varsayılan DDX/DDV mekanizmasını genişletmek için birkaç yol vardır. Şunları yapabilirsiniz:

- Yeni veri türleri ekleyin.

    ```cpp
    CTime
    ```

- Yeni Exchange yordamları (DDX_) ekleyin.

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- Yeni doğrulama yordamları (DDV_) ekleyin.

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- Doğrulama yordamlarına rastgele ifadeler geçirin.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > Bu tür rastgele ifadeler ClassWizard tarafından düzenlenemez ve bu nedenle özel biçim yorumlarının (//{{AFX_DATA_MAP (CMyClass)) dışına taşınmalıdır.

`DoDialogExchange`Üye işlevine, karma Exchange ve doğrulama işlevi çağrılarında Koşullular veya diğer geçerli C++ deyimlerini içermesini sağlayabilirsiniz.

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
> Yukarıda gösterildiği gibi bu kod, ClassWizard tarafından düzenlenemez ve yalnızca özel biçim açıklamalarının dışında kullanılmalıdır.

## <a name="classwizard-support"></a>ClassWizard desteği

ClassWizard, kendi DDX_ ve DDV_ yordamlarını ClassWizard Kullanıcı arabirimiyle tümleştirmenize izin vererek DDX/DDV özelleştirmelerinin bir alt kümesini destekler. Bunun yapılması yalnızca bir projede veya birçok projede belirli DDX ve DDV yordamlarını yeniden kullanmayı planlıyorsanız maliyet avantajına sahiptir.

Bunu yapmak için, DDX. CLW içinde özel girişler yapılır (Visual C++ önceki sürümleri, bu bilgileri APSTUDIO.INI içinde veya projenizin). CLW dosyası. Özel girişler, projenizin [genel bilgi] bölümünde girilebilir. CLW dosyası veya \Program Files\Microsoft Visual Studio\Visual C++ \Bin dizinindeki DDX. CLW dosyasının [ExtraDDX] bölümünde. Zaten mevcut değilse, DDX. CLW dosyasını oluşturmanız gerekebilir. Özel DDX_/DDV_ yordamlarını yalnızca belirli bir projede kullanmayı planlıyorsanız, girdileri projenizin [genel bilgi] bölümüne ekleyin. Bunun yerine CLW dosyası. Yordamları birçok proje üzerinde kullanmayı planlıyorsanız,, DDX. CLW 'ın [ExtraDDX] bölümüne girdileri ekleyin.

Bu özel girdilerin genel biçimi:

> ExtraDDXCount =*n*

Burada *n* , ExtraDDX sayısıdır mi? formun takip edilecek satırlar

> ExtraDDX? =*anahtarlar*; *vb anahtarları*; *istem*; *tür*; *InitValue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

olmadığı? , listede hangi DDX türünün tanımlanmakta olduğunu belirten bir 1- *n* sayısıdır.

Her alan bir '; ' karakteriyle sınırlandırılmıştır. Alanlar ve amaçları aşağıda açıklanmıştır.

- *belirlenmesine*

  Bu değişken türüne izin verilen iletişim kutusu denetimlerine işaret eden tek karakterlerin bir listesi.

  |Karakter|İzin verilen denetim|
  |-|-|
  E | düzenle
  C | iki durumlu onay kutusu
  c | Üçlü durum onay kutusu
  R | bir gruptaki ilk radyo düğmesi
  L | sıralanmış olmayan liste kutusu
  l | sıralanmış liste kutusu
  M | Birleşik giriş kutusu (düzenleme öğesi ile)
  N | sıralı olmayan bırakma listesi
  n | sıralanmış bırakma listesi
  1 | DDX ekleme listenin baş öğesine eklenmelidir (varsayılan, tail 'e Ekle), bu genellikle ' Control ' özelliğini aktarabilen DDX yordamları için kullanılır.

- *vb anahtarları*

  Bu alan yalnızca, VBX denetimleri için 16 bit üründe kullanılır (32 bit üründe VBX denetimleri desteklenmez)

- *isteme*

  Özellik Birleşik giriş kutusuna yerleştirilecek dize (tırnak işareti yok)

- *türüyle*

  Üst bilgi dosyasında yayma türü için tek tanımlayıcı. Yukarıdaki örnekte DDX_Time, bu, CTime olarak ayarlanır.

- *vb anahtarları*

  Bu sürümde kullanılmıyor ve her zaman boş olmalıdır

- *InitValue*

  İlk değer — 0 veya boş. Boşsa, uygulama dosyasının//{{AFX_DATA_INIT bölümünde başlatma satırı yazılmaz. `CString` `CTime` Doğru başlatmayı garanti eden oluşturuculara sahip C++ nesneleri (örneğin,, vb.) için boş bir giriş kullanılmalıdır.

- *DDX_Proc*

  DDX_ yordamı için tek tanımlayıcı. C++ işlev adı "DDX_" ile başlamalı, ancak tanımlayıcıda "DDX_" içermemelidir \<DDX_Proc> . Yukarıdaki örnekte, \<DDX_Proc> tanımlayıcı zaman olabilir. ClassWizard, {{AFX_DATA_MAP bölümündeki uygulama dosyasına işlev çağrısını yazdığında, bu adı DDX_ ekler ve bu nedenle DDX_Time 'e gelir.

- *açıklamanın*

  Bu DDX ile değişken için iletişim kutusunda gösterilecek açıklama. Buraya istediğiniz metni koyun ve genellikle DDX/DDV çiftinin gerçekleştirdiği işlemi açıklayan bir şey sağlayın.

- *DDV_Proc*

  Girişin DDV kısmı isteğe bağlıdır. Tüm DDX yordamlarının karşılık gelen DDV yordamları yoktur. Genellikle, aktarımın bir integral parçası olarak doğrulama aşamasını eklemek daha uygundur. Bu durum genellikle DDV yordamınız parametre olmadan DDV yordamlarını desteklemediği için bir parametre gerektirmediği durumdur.

- *değişkeni*

  DDV_ yordamı için tek tanımlayıcı. C++ işlev adı "DDV_" ile başlamalı, ancak tanımlayıcıda "DDX_" içermemelidir \<DDX_Proc> .

  *arg* , 1 veya 2 DDV args ile izlenir:

  - *promptN*

      Düzenleme öğesinin üstüne yerleştirilecek dize (Hızlandırıcı için &).

  - *fmtN*

      Bağımsız değişken türü için Biçim karakteri, aşağıdakilerden biri:

      |Karakter|Tür|
      |-|-|
      |d | int|
      |u | unsigned int|
      |D | long int (diğer bir deyişle, Long)|
      |U | uzun işaretsiz (yani DWORD)|
      |f | float|
      |F | double|
      |s | string|

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
