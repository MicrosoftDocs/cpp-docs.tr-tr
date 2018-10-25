---
title: 'TN020: Adlandırma ve numaralandırma kuralları kimliği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.id
dev_langs:
- C++
helpviewer_keywords:
- TN020
- resource identifiers, naming and numbering
- resource identifiers
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b66fa88a98f800c77e2b6b0a731bbd40df9eb9d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054637"
---
# <a name="tn020-id-naming-and-numbering-conventions"></a>TN020: Kimlik Adlandırma ve Numaralandırma Kuralları

Bu Not, kimlik adlandırma ve kaynakları, komutları, dizeler, denetimleri ve alt pencereler için MFC 2.0 kullanan numaralandırma kuralları açıklar.

MFC kimlik adlandırma ve numaralandırma kuralları aşağıdaki gereksinimleri karşılaması için tasarlanmıştır:

- Visual C++ kaynak Düzenleyicisi tarafından desteklenen MFC uygulamaları ve MFC Kitaplığı kullanılan tutarlı bir kimliği adlandırma standardı sağlar. Bu türü ve bir kaynaktan kimliğini kaynağından yorumlamak Programcı kolaylaştırır

- Belirli türlerdeki kimlikleri arasında güçlü 1-1 ilişki vurgulayın.

- Windows kimlikleri adlandırma zaten yaygın olarak kullanılan standartlara uygun.

- Bölüm kimliği numaralandırma alanı. Kimlik numaraları, Programcı, MFC, Windows ve Visual C++ ile düzenlenmiş kaynakları tarafından atanabilir. Uygun bölümleme, çoğaltma kimliği sayıların önlenmesine yardımcı olur.

## <a name="the-id-prefix-naming-convention"></a>Kimlik öneki adlandırma kuralı

Bir uygulamada birden fazla kimlikleri ortaya çıkabilir. MFC kodu adlandırma kuralı, farklı ön ekleri farklı kaynak türleri için tanımlar.

MFC, birden çok kaynak türü için geçerli bir kaynak kimliği belirtmek için "IDR_" öneki kullanır. Örneğin, belirli bir çerçeve penceresi için menü, Hızlandırıcı, dize ve simgeyi bir kaynağı göstermek için aynı "IDR_" önekini MFC kullanır. Aşağıdaki tabloda, çeşitli ön ekleri ve bunların kullanımını gösterir:

|Ön eki|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|------------|---------|
|IDR_|(Menüleri, Hızlandırıcılar ve şeritler için öncelikli olarak kullanılır) birden çok kaynak türleri için.|
|IDD_|İletişim şablon kaynakları (örneğin, IDD_DIALOG1).|
|IDC_|İmleç kaynakları.|
|IDI_|Simge kaynakları.|
|IDB_|Bit eşlem kaynakları.|
|IDS_|Dize kaynakları.|

Bir iletişim kaynağı içinde MFC, bu kuralları aşağıdaki gibidir:

|Ön eki veya etiketi|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|---------------------|---------|
|IDOK, IDCANCEL|Standart düğme için kimlikleri.|
|IDC_|Diğer bir iletişim kutusu denetimleri için.|

"IDC_" öneki işaretçiler için de kullanılır. Tipik bir uygulaması birkaç imleç ve birçok iletişim kutusu denetimleri olduğundan bu ad çakışması genellikle bir sorun değildir.

Bir menü kaynağı içinde bu kuralları MFC aşağıdaki gibidir:

|Ön eki|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|------------|---------|
|IDM_|Menü öğeleri için MFC komut mimarisi kullanmayın.|
|ID_|MFC kullanan menü komutlarını mimarisi komutu.|

MFC komut mimarisi aşağıdaki komutları bir ON_COMMAND komut işleyicisi olmalıdır ve bir on_update_command_uı işleyicisi olabilir. Bu komut işleyicileri MFC komut mimarisi izlerseniz, bunlar düzgün bir menü komutu, bir araç çubuğu düğmesini veya bir iletişim çubuğu düğme bağlı olan çalışmayacaktır. Aynı "ID_" ön eki programın ileti çubuğunda görüntülenen bir menü istem dizesi için de kullanılır. Uygulamanızdaki menü öğelerinin çoğu MFC komut kuralları izlemelidir. Tüm standart komut kimlikleri (örneğin, ıd_fıle_new) Bu kuralı uygulayın.

MFC "IDP_" özel biçimi dizeleri (yerine "IDS_") olarak da kullanır. İstemleri, diğer bir deyişle, ileti kutularında kullanılan dizelerin dizelerdir "IDP_" ön ekine sahip. "IDP_" dizeler, program tarafından belirlenen dize yer tutucu olarak "%1" ve "%2" içerebilir. "IDP_" dizeleri, genellikle Yardım konuları ilişkili olan ve "IDS_" dizeleri yapın. Her zaman yerelleştirilmiş dizeleri "IDP_" ve "IDS_" dizeleri yerelleştirilmemiş.

MFC Kitaplığı "IDW_" ön eki özel form denetiminin kimlikleri (yerine "IDC_") olarak da kullanır. Bu kimliklerinin alt pencereler gibi görünümler ve ayırıcılar framework sınıfları tarafından atanır. MFC Uygulama kimlikleri "İle AFX_" öneki alır.

## <a name="the-id-numbering-convention"></a>Kimliği numaralandırma kuralı

Aşağıdaki tabloda, geçerli aralıklar kimliklerini belirli türlerini listeler. Bazı sınırlar teknik uygulama limitlerdir ve diğerleri Windows önceden tanımlanmış kimlikler ya da MFC varsayılan uygulamaları çakışmadan kimliklerinizi önlemek üzere tasarlanmış kurallardır.

Önerilen aralıklar içinde tüm kimlikleri tanımladığınız kesinlikle öneririz. 0 kullanılmadığından bu aralıklarının alt sınırı 1'dir. Genel kuralı kullanın ve 100 veya 101 ilk kimlik olarak kullanmak öneririz.

|Ön eki|Kaynak türü|Geçerli aralık|
|------------|-------------------|-----------------|
|IDR_|birden çok|1 ile 0x6FFF|
|IDD_|iletişim kutusu şablonları|1 ile 0x6FFF|
|IDC_, IDI_, IDB_|imleçler, simgeler, bit eşlemler|1 ile 0x6FFF|
|IDS_, IDP_|Genel dizeleri|1 ile 0x7FFF|
|ID_|komutlar|0x8000 ile 0xDFFF|
|IDC_|denetimler|8 ile 0xDFFF|

Bu aralığı sınırları nedenleri:

- Kural gereği, 0 kimlik değerini kullanılmaz.

- Windows uygulama kısıtlamaları gerçek kaynak kimlikleri 0x7FFF eşit veya daha az olacak şekilde kısıtlayın.

- MFC'nin iç framework Bu aralıklar ayırır:

   - 0x7000 0x7FFF aracılığıyla (afxres.h bakın)

   - 0xE000 0xEFFF aracılığıyla (afxres.h bakın)

   - 16000 18000 (afxribbonres.h bakın) aracılığıyla

   Bu aralıklar, MFC uygulamaları gelecekte değişebilir.

- Çeşitli Windows sistem komutlarını ile 0xFFFF 0xF000 aralığı kullanın.

- Denetim Kimliği 1 ile 7 arasında IDOK ve IDCANCEL gibi standart denetimler için ayrılmıştır.

- 0x8000 ile 0xFFFF dizeler için çeşitli komutlar için menü istemleri için ayrılmıştır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

