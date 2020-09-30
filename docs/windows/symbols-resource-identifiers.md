---
title: Kaynak tanımlayıcıları (semboller) (C++)
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
ms.openlocfilehash: 1a01c127c69bb54209ecc059394eb85ef0ca4eeb
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509619"
---
# <a name="resource-identifiers-symbols-c"></a>Kaynak tanımlayıcıları (semboller) (C++)

Sembol, bir sembol değeriyle (tamsayı) eşlenmiş bir sembol adı (metin dizesi) olan iki bölümden oluşan bir kaynak tanımlayıcısıdır (ID). Örneğin:

```cpp
IDC_EDITNAME = 5100
```

Sembol adları genellikle tanımlayıcılar olarak adlandırılır.

Semboller, kaynaklar ve Kullanıcı arabirimi nesnelerine, hem kaynak kodunuzda hem de kaynak düzenleyicilerinde çalışırken bunlarla ilgili açıklayıcı bir yol sağlar. Sembolleri, [kaynak sembolleri iletişim kutusunu](./creating-new-symbols.md)kullanarak bir uygun yerde görüntüleyebilir ve yönetebilirsiniz.

Uygulamanız boyut ve gelişmiş algoritmaların mümkündür büyüdükçe, kaynak ve sembol sayısını de vardır. Birçok dosya genelinde dağılmış çok sayıda sembol izlemek zor olabilir. **Kaynak sembolleri** iletişim kutusu, ' de kullanabileceğiniz bir merkezi araç sunarak sembol yönetimini basitleştirir:

- [Sembol oluştur](../windows/creating-new-symbols.md)

- [Sembolleri Yönet](../windows/changing-a-symbol-or-symbol-name-id.md)

- [Önceden tanımlanmış sembol kimliklerini görüntüle](../windows/predefined-symbol-ids.md)

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda, kaynak [düzenleyicileri](../windows/resource-editors.md) kaynak için varsayılan bir ad sağlar, örneğin, `IDC_RADIO1` ve kendisine bir değer atar. Ad ve değer tanımı `Resource.h` dosyada depolanır.

> [!NOTE]
> Bir. rc dosyasından bir. rc dosyasından kaynak veya kaynak nesneleri kopyalarken, Visual C++ var olan dosyadaki sembol adlarıyla veya değerlerle çakışmayı önlemek için, aktarılan kaynağın sembol değerini veya sembol adını ve değerini değiştirebilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak düzenleyicileri](../windows/resource-editors.md)<br/>
