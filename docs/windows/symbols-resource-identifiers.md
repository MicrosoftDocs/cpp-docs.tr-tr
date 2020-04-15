---
title: Kaynak Tanımlayıcıları (Semboller) (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.identifiers
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
ms.openlocfilehash: c6b3cf7d3edfc870164645632bb07bf49c792a48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359895"
---
# <a name="resource-identifiers-symbols-c"></a>Kaynak Tanımlayıcıları (Semboller) (C++)

Sembol, örneğin bir sembol değerine (tamsayı) eşlenen iki bölümden, bir sembol adından (metin dizesi) oluşan bir kaynak tanımlayıcısýr (ID):

```cpp
IDC_EDITNAME = 5100
```

Sembol adları genellikle tanımlayıcıolarak adlandırılır.

Semboller, hem kaynak kodunuzda hem de kaynak düzenleyicilerinde bunlarla çalışırken kaynaklara ve kullanıcı arabirimi nesnelerine atıfta bulunarak açıklayıcı bir yol sağlar. [Kaynak Sembolleri iletişim kutusunu](../windows/viewing-resource-symbols.md)kullanarak sembolleri uygun bir yerde görüntüleyebilir ve işleyebilirsiniz.

Uygulamanız boyutu ve gelişmişlik büyüdükçe, bu yüzden kaynak ve sembol sayısı yok. Çeşitli dosyalara dağılmış çok sayıda simgeyi izlemek zor olabilir. **Kaynak Sembolleri** iletişim kutusu, aşağıdakileri yapabileceğiniz merkezi bir araç sunarak sembol yönetimini basitleştirir:

- [Semboller Oluştur](../windows/creating-new-symbols.md)

- [Sembolleri Yönet](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Önceden Tanımlanmış Sembol Tanımlarını Görüntüle](../windows/predefined-symbol-ids.md)

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda, [kaynak düzenleyicileri](../windows/resource-editors.md) kaynak `IDC_RADIO1`için varsayılan bir ad sağlar, örneğin, ve ona bir değer atar. Ad artı değer tanımı `Resource.h` dosyada depolanır.

> [!NOTE]
> Kaynakları veya kaynak nesnelerini bir .rc dosyasından diğerine kopyalarken, Visual C++ varolan dosyadaki sembol adları veya değerlerle çakışmaları önlemek için aktarılan kaynağın sembol değerini veya sembol adını ve değerini değiştirebilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak Dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
