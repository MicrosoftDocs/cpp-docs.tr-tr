---
description: 'Daha fazla bilgi edinin: TN020: KIMLIK adlandırma ve numaralandırma kuralları'
title: 'TN020: Kimlik Adlandırma ve Numaralandırma Kuralları'
ms.date: 11/04/2016
f1_keywords:
- vc.id
helpviewer_keywords:
- TN020
- resource identifiers, naming and numbering
- resource identifiers
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
ms.openlocfilehash: 85f59e45ec9d4ce748515cf638f4fb4cf33c7d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215878"
---
# <a name="tn020-id-naming-and-numbering-conventions"></a>TN020: Kimlik Adlandırma ve Numaralandırma Kuralları

Bu notta, MFC 2,0 ' nin kaynaklar, komutlar, dizeler, denetimler ve alt pencereler için kullandığı KIMLIK adlandırma ve numaralandırma kuralları açıklanmaktadır.

MFC KIMLIK adlandırma ve numaralandırma kuralları aşağıdaki gereksinimleri karşılayacak şekilde tasarlanmıştır:

- MFC kitaplığı ve Visual C++ kaynak Düzenleyicisi tarafından desteklenen MFC uygulamaları arasında kullanılan tutarlı bir KIMLIK adlandırma standardı sağlayın. Bu, programcının bir kaynağın türünü ve kaynağını KIMLIĞINDEN yorumlamasını kolaylaştırır.

- Belirli kimlik türleri arasındaki güçlü 1 ila 1 ilişkiyi vurgulayın.

- Windows 'daki adlandırma kimlikleri için zaten yaygın olarak kullanılan standartlara uygun.

- KIMLIK numaralandırma alanını bölümlemek. KIMLIK numaraları, programcı, MFC, Windows ve Visual C++ düzenlenmiş kaynaklarla atanabilir. Uygun bölümlendirme, KIMLIK numaralarının çoğaltılmasını önlemeye yardımcı olur.

## <a name="the-id-prefix-naming-convention"></a>KIMLIK ön eki adlandırma kuralı

Bir uygulamada çeşitli kimlik türleri meydana gelebilir. MFC KIMLIK adlandırma kuralı farklı kaynak türleri için farklı ön ekleri tanımlar.

MFC, birden çok kaynak türü için geçerli olan bir kaynak KIMLIĞI belirtmek için "IDR_" önekini kullanır. Örneğin, belirli bir çerçeve penceresinde, MFC bir menü, Hızlandırıcı, dize ve simge kaynağını göstermek için aynı "IDR_" önekini kullanır. Aşağıdaki tabloda çeşitli ön ekler ve kullanımları gösterilmektedir:

|Ön ek|Kullanın|
|------------|---------|
|IDR_|Birden çok kaynak türü için (öncelikle menüler, Hızlandırıcılar ve şeritler için kullanılır).|
|IDD_|İletişim kutusu şablon kaynakları için (örneğin, IDD_DIALOG1).|
|IDC_|İmleç kaynakları için.|
|IDI_|Simge kaynakları için.|
|IDB_|Bit eşlem kaynakları için.|
|IDS_|Dize kaynakları için.|

Bir iletişim kutusu kaynağı içinde, MFC aşağıdaki kurallara uyar:

|Önek veya etiket|Kullanın|
|---------------------|---------|
|ıDOK, ıDCANCEL|Standart gönderme düğmesi kimlikleri için.|
|IDC_|Diğer iletişim kutusu denetimleri için.|

"IDC_" öneki Ayrıca imleçler için de kullanılır. Tipik bir uygulama birkaç imleç ve birçok iletişim kutusu denetimine sahip olacağı için bu adlandırma çakışmasına genellikle sorun değildir.

Bir menü kaynağı içinde, MFC aşağıdaki kurallara uyar:

|Ön ek|Kullanın|
|------------|---------|
|IDM_|MFC komut mimarisini kullanmayan menü öğeleri için.|
|ID_|MFC komut mimarisini kullanan menü komutları için.|

MFC komut mimarisini izleyen komutların bir ON_COMMAND komut işleyicisi olmalıdır ve bir ON_UPDATE_COMMAND_UI işleyicisine sahip olabilir. Bu komut işleyicileri MFC komut mimarisini izlerse, bir menü komutuna, bir araç çubuğu düğmesine veya iletişim çubuğu düğmesine bağlanıp bağlanmadığını doğru şekilde çalışır. Aynı "ID_" öneki Ayrıca programın ileti çubuğunda görüntülenen bir menü istemi dizesi için de kullanılır. Uygulamanızdaki menü öğelerinin çoğu MFC komut kurallarını izlemelidir. Standart komut kimliklerinin tamamı (örneğin, ID_FILE_NEW) Bu kuralı izleyin.

MFC Ayrıca, özel dizeler biçimi olarak "IDP_" kullanır ("IDS_" yerine). "IDP_" ön ekine sahip dizeler istemlerdir, diğer bir deyişle ileti kutularında kullanılan dizeler. "IDP_" dizeleri, program tarafından belirlenen dizelerin yer tutucuları olarak "%1" ve "%2" içerebilir. "IDP_" dizeleri genellikle bunlarla ilişkili Yardım konularına sahiptir ve "IDS_" dizeleri değildir. "IDP_" dizeleri her zaman yereldir ve "IDS_" dizeleri yerelleştirilemeyebilir.

MFC Kitaplığı Ayrıca "IDW_" önekini özel denetim kimliği biçimi olarak kullanır ("IDC_" yerine). Bu kimlikler, çerçeve sınıfları tarafından görünümler ve bölümlendiricileri gibi alt pencereler için atanır. MFC Uygulama kimliklerine "AFX_" ön eki uygulanır.

## <a name="the-id-numbering-convention"></a>ID-Numbering kuralı

Aşağıdaki tabloda, belirli türlerin kimlikleri için geçerli aralıklar listelenmektedir. Limitlerin bazıları teknik uygulama sınırlamalarıdır ve diğerleri, kimliklerinizin Windows önceden tanımlı kimlikler veya MFC varsayılan uygulamalarıyla çakışmasını engellemek için tasarlanan kurallardır.

Önerilen aralıkların içindeki tüm kimlikleri tanımlamanızı önemle tavsiye ederiz. 0 kullanılmadığından bu aralıkların alt sınırı 1 ' dir. Ortak kuralını kullanmanızı ve ilk KIMLIK olarak 100 veya 101 ' i kullanmanızı öneririz.

|Ön ek|Kaynak türü|Geçerli Aralık|
|------------|-------------------|-----------------|
|IDR_|birden çok|1 ila 0x6FFF|
|IDD_|iletişim kutusu şablonları|1 ila 0x6FFF|
|IDC_, IDI_, IDB_|imleçler, simgeler, bit eşlemler|1 ila 0x6FFF|
|IDS_, IDP_|Genel dizeler|1 ile 0x7FFF|
|ID_|komutlar|0x8000 ila 0xDFFF|
|IDC_|denetimler|8 ila 0xDFFF|

Bu Aralık sınırlarının nedenleri:

- Kurala göre, 0 ' ın ID değeri kullanılmaz.

- Windows uygulama sınırlamaları, doğru kaynak kimliklerini 0x7FFF değerinden küçük veya buna eşit olacak şekilde kısıtlar.

- MFC 'nin iç çerçevesi bu aralıkları ayırır:

  - 0x7000 ile 0x7FFF (bkz. afxres. h)

  - 0xEFFF ile 0xE000 (bkz. afxres. h)

  - 16000 ile 18000 (bkz. afxribbonres. h)

  Bu aralıklar, gelecekteki MFC uygulamalarında değişebilir.

- Birkaç Windows sistem komutu, 0xF000 ile 0xFFFF aralığını kullanır.

- 1 ile 7 arasındaki Denetim kimlikleri ıDOK ve ıDCANCEL gibi standart denetimler için ayrılmıştır.

- Dizeler için 0x8000 ile 0xFFFF arasındaki Aralık menü istemlerine yönelik komut istemleri için ayrılmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
