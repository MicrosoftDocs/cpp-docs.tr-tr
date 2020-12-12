---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: sembolleri yönetme'
title: 'Nasıl yapılır: sembolleri yönetme'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.changing
- vc.editors.symbol.restrictions.name
- vc.editors.symbol.changing.value
- vc.editors.symbol.restrictions.value
- vc.editors.symbol.changing.header
- vc.editors.symbol.changing.unassigned
- vc.editors.symbol.shared.calculated
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
- symbols [C++], value restrictions
- restrictions, symbol values
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
- symbols [C++], read-only
- symbols [C++], shared
- symbols [C++], calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 2a7bdc6994bfcdadc9b7d1d5b98350fcd47ad6fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118231"
---
# <a name="how-to-manage-symbols"></a>Nasıl yapılır: sembolleri yönetme

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda, geliştirme ortamı buna Örneğin, varsayılan bir sembol adı atar `IDD_DIALOG1` . Varsayılan sembol adını değiştirmek veya bir kaynakla ilişkilendirilmiş olan herhangi bir sembolün adını değiştirmek için [Özellikler penceresi](/visualstudio/ide/reference/properties-window) kullanabilirsiniz.

Tek bir kaynakla ilişkili semboller için, sembol değerini değiştirmek için **Özellikler** penceresini de kullanabilirsiniz. Kaynak [sembolleri iletişim kutusunu](./creating-new-symbols.md) , şu anda bir kaynağa atanmamış sembollerin değerini değiştirmek için kullanabilirsiniz.

Normalde tüm sembol tanımları ' de kaydedilir `Resource.h` . Bununla birlikte, örneğin, aynı dizinde birden fazla kaynak dosyası ile çalışabilmek için bu dosya adını da değiştirmeniz gerekebilir.

> [!NOTE]
> Projeniz zaten bir. rc dosyası içermiyorsa bkz. [nasıl yapılır: kaynak oluşturma](how-to-create-a-resource-script-file.md).

## <a name="symbol-name-restrictions"></a>Sembol Adı Kısıtlamaları

Sembol adlarında kısıtlamalar aşağıdaki gibidir:

- Üst bilgi dosyalarında çakışan sembol tanımlarını engellemek için tüm [semboller](symbols-resource-identifiers.md) uygulamanın kapsamı içinde benzersiz olmalıdır.

- Bir sembol adı için geçerli karakterler A-Z, a-z, 0-9 ve alt çizgi (_) içerir.

- Sembol adları bir sayıyla başlayamaz ve 247 karakterle sınırlıdır.

- Sembol adlarında boşluk bulunamaz.

- Sembol adları büyük/küçük harfe duyarlı değildir, ancak ilk sembol tanımının durumu korunur.

   Sembolleri tanımlayan üstbilgi dosyası, bir kaynak dosyasında tanımlanan kaynakları başvurmak için hem kaynak derleyicisi/Düzenleyici hem de C++ programları tarafından kullanılır. Yalnızca büyük/küçük harf bakımından farklı olan iki sembol adı için, kaynak derleyicisi/düzenleyici iki ayrı sembol görür.

> [!NOTE]
> Aşağıda özetlenen standart sembol adı düzenini (KIMLIK * _ [anahtar sözcük]) ve sembol adınızın kaynak betiği derleyicisi tarafından bilinen bir anahtar sözcükle aynı olması durumunda, kaynak betik dosyasını oluşturmaya çalışmak, tanılanması zor olan düzensiz rastgele bir hata oluşturulmasına neden olur. Bunu engellemek için standart adlandırma şemasına bağlı kalın.

Sembol adlarında temsil ettikleri kaynak veya nesne türünü gösteren açıklayıcı ön ekler vardır. Bu açıklayıcı önekler metin birleşim KIMLIĞIYLE başlar. Microsoft Foundation Class (MFC) kitaplığı, aşağıdaki tabloda gösterilen sembol adlandırma kurallarını kullanır:

|Kategori|Ön ek|Kullanın|
|--------------|------------|---------|
|Kaynaklar|IDR_, IDD_, IDC_, IDI_, IDB_|Hızlandırıcı veya menü (ve ilişkili veya özel kaynaklar), iletişim kutusu, imleç, simge, bit eşlem|
|Menü öğeleri|ID_|Menü öğesi|
|Komutlar|ID_|Komut|
|Denetimler ve alt pencereler|IDC_|Denetim|
|Dizeler|IDS_|Dize tablosunda dize|
|MFC|AFX_|Önceden tanımlanmış MFC sembolleri için ayrılmıştır|

### <a name="to-change-a-symbol-name-id"></a>Bir sembol adını (ID) değiştirmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), kaynağı seçin.

1. **Özellikler** penceresinde, yeni bir sembol adı yazın veya **kimlik** kutusunda varolan semboller listesinden seçin.

   Yeni bir sembol adı yazarsanız, otomatik olarak bir değer atanır.

> [!NOTE]
> Kaynak [sembolleri iletişim kutusunu](./creating-new-symbols.md) , şu anda bir kaynağa atanmamış sembollerin adlarını değiştirmek için kullanabilirsiniz.

## <a name="symbol-value-restrictions"></a>Sembol Değeri Kısıtlamaları

Bir sembol değeri, Önişlemci yönergeleri için normal şekilde ifade edilen herhangi bir tamsayı olabilir `#define` . Sembol değerlerine ilişkin bazı örnekler aşağıda verilmiştir:

```
18
4001
0x0012
-3456
```

Hızlandırıcılar, bit eşlemler, imleçler, iletişim kutuları, simgeler, menüler, dize tabloları ve sürüm bilgileri gibi kaynakların sembol değerleri, 0 ile 32.767 arasında ondalık sayı olmalıdır ancak onaltılık olamaz. İletişim kutusu denetimleri veya dize tablosundaki bağımsız dizeler gibi kaynakların bölümlerinin sembol değerleri, 0 ile 65.534 arasında veya-32.768 ile 32.767 arasında olabilir. Sayı aralıkları hakkında daha fazla bilgi için bkz. [TN023: Standart MFC kaynakları](../mfc/tn023-standard-mfc-resources.md).

Kaynak sembolleri 16 bit sayılardır. Bunları imzalanmış veya imzasız olarak girebilirsiniz; ancak, bunlar dahili olarak işaretsiz tamsayılar olarak kullanılır, bu nedenle negatif sayılar karşılık gelen pozitif değere alınacaktır.

Sembol değerlerinin bazı sınırlamaları şunlardır:

- Visual Studio geliştirme ortamı ve MFC özel amaçlar için bazı sayı aralıklarını kullanır. En önemli bit kümesine (-32.768-1 veya 32.768-65.534) sahip tüm sayılar, oturum açma 'ya bağlı olarak MFC tarafından ayrılmıştır.

- Diğer sembol dizelerini kullanarak bir sembol değeri tanımlayamazsınız. Örneğin, aşağıdaki sembol tanımı desteklenmez:

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- Önişlemci makrolarını bağımsız değişkenlerle birlikte değer tanımları olarak kullanamazsınız. Aşağıdaki örnek, `ID` derleme zamanında ne kadar değerlendirdiğine bakılmaksızın geçerli bir ifade değildir:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

- Uygulamanızda, ifadelerle tanımlanmış sembolleri içeren mevcut bir dosya olabilir.

### <a name="to-change-a-symbol-value"></a>Bir sembol değerini değiştirmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), kaynağı seçin.

1. **Özellikler** penceresinde, bir eşittir işareti ve ardından **kimlik** kutusunda bir tamsayı olan sembol adını yazın, örneğin:

    ```
    IDC_EDITNAME=5100
    ```

   Yeni değer, projeyi bir sonraki kaydedişinizde sembol üstbilgi dosyasında depolanır. KIMLIK kutusunda yalnızca sembol adı görünür kalır ve eşittir işareti ve değeri doğrulandıktan sonra görüntülenmez.

## <a name="change-or-delete-symbols"></a>Sembolleri değiştirme veya silme

[Kaynak sembolleri iletişim kutusunda](./creating-new-symbols.md), zaten bir kaynağa veya nesneye atanmamış mevcut sembolleri düzenleyebilir veya silebilirsiniz.

### <a name="to-change-an-unassigned-symbol"></a>Atanmamış bir sembolü değiştirmek için

1. **Ad** kutusunda atanmamış simgesini seçin ve **Değiştir**' i seçin.

1. Sembolü **Değiştir** iletişim kutusunda belirtilen kutulara simgenin adını veya değerini düzenleyin.

> [!NOTE]
> Bir kaynağa veya nesneye atanan bir sembolü değiştirmek için kaynak Düzenleyicisi veya **Özellikler** penceresini kullanmanız gerekir.

### <a name="to-delete-an-unassigned-unused-symbol"></a>Atanmamış (kullanılmamış) bir sembolü silmek için

**Kaynak sembolleri** iletişim kutusunda silmek istediğiniz simgeyi seçin ve **Sil**' i seçin.

> [!NOTE]
> Kaynak dosyasında kullanılmamış bir sembolü silmeden önce programın başka bir yerinde veya derleme zamanında dahil edilen kaynak dosyaları tarafından kullanılmadığından emin olun.

## <a name="include-symbols"></a>Sembolleri dahil et

Geliştirme ortamı, başka bir uygulama tarafından oluşturulan bir kaynak dosyasını ilk kez okuduğunda, eklenen tüm üst bilgi dosyalarını salt okunur olarak işaretler. Bununla birlikte, ek salt okunurdur sembol üstbilgi dosyaları eklemek için [kaynak içerme iletişim kutusunu](./how-to-include-resources-at-compile-time.md) da kullanabilirsiniz.

Salt okunurdur sembol tanımları kullanmak isteyebileceğiniz bir nedeni, birkaç proje arasında paylaşmayı planladığınız sembol dosyaları içindir.

Sembol değerlerini tanımlamak için basit tamsayılar yerine ifadeler kullanan sembol tanımlarına sahip mevcut kaynaklarınız varsa, dahil edilen sembol dosyalarını da kullanabilirsiniz. Örneğin:

```cpp
#define   IDC_CONTROL1 2100
#define   IDC_CONTROL2 (IDC_CONTROL1+1)
```

Ortam Bu hesaplanan sembolleri şu kadar süre içinde doğru yorumlayacak:

- Hesaplanan semboller salt okunurdur bir sembol dosyasına yerleştirilir.

- Kaynak dosyanız, bu hesaplanan sembollerin zaten atandığı kaynakları içerir.

- Sayısal bir ifade bekleniyor.

> [!NOTE]
> Bir dize veya sayısal ifade bekleniyorsa ifade değerlendirilmez.

### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>Kaynak dosyanıza paylaşılan (salt okuma) semboller eklemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp [kaynak içermeler](./how-to-include-resources-at-compile-time.md)' i seçin.

1. Salt **okuma sembolü yönergeleri** kutusunda, `#include` salt okuma simgelerinin saklanmasını istediğiniz dosyayı belirtmek için derleyici yönergesini kullanın.

   `Resource.h`Ana sembol üstbilgi dosyası tarafından normalde kullanılan dosya adı olduğundan, dosyayı çağırmayın.

   > [!NOTE]
   > **Salt oku sembol yönergeleri** kutusuna yazdığınız şeyler, tam olarak siz yazarken kaynak dosyasına dahil edilir. Yazımın yazım veya sözdizimi hataları içermediğinden emin olun.

   Yalnızca sembol tanımlarına sahip dosyaları dahil etmek için **salt okunurdur sembol yönergeleri** kutusunu kullanın. Kaynak tanımlarını eklemeyin, başka bir deyişle dosya kaydedildiğinde yinelenen kaynak tanımları oluşturulacaktır.

1. Sembolleri belirttiğiniz dosyaya yerleştirin.

   Bu şekilde bulunan dosyalardaki semboller, kaynak dosyanızı her açışınızda değerlendirilir, ancak dosyanızı kaydettiğinizde diskte değiştirilmez.

1. **Tamam**’ı seçin.

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>Kaynak sembolü üstbilgi dosyasının adını değiştirmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp [kaynak içermeler](./how-to-include-resources-at-compile-time.md)' i seçin.

1. **Sembol üstbilgi dosyası** kutusuna ekleme dosyası için yeni bir ad yazın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak tanımlayıcıları (semboller)](symbols-resource-identifiers.md)<br/>
[Nasıl yapılır: semboller oluşturma](creating-new-symbols.md)<br/>
[Önceden tanımlanmış sembol kimlikleri](predefined-symbol-ids.md)<br/>
