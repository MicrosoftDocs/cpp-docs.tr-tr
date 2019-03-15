---
title: Visual C++ Belge Etiketleri için Sınırlayıcılar
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
ms.openlocfilehash: fec10171270a76ed90e2a7459103a148af0ba735
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824160"
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Visual C++ Belge Etiketleri için Sınırlayıcılar

Belge etiketleri gösteren bir belge açıklaması burada başlar ve biter derleyici sınırlayıcılar gerektirir.

Aşağıdaki türde sınırlayıcıları ile XML belge etiketleri kullanabilirsiniz:

| | |
|-|-|
| `///` | Bu belge örneklerde gösterildiği ve Visual C++ proje şablonları tarafından kullanılan biçimidir.  |
| `/** */`  | Çok satırlı sınırlayıcı olarak bu kullanılır.  |

Var olan bazı biçimlendirme kurallarını kullanarak `/** */` sınırlayıcılar:

- İçeren bir satır için `/**` ayırıcı, boşluk, satır satır geri kalanında ise açıklamalarına işlenmedi. İlk karakterin boşluk varsa bu boşluk karakteri göz ardı edilir ve satırın geri kalanını işlenir. Aksi takdirde, tüm metin satırının sonra `/**` sınırlayıcı açıklamayı bir parçası olarak işlenir.

- İçeren bir satır için `*/` varsa yalnızca boşluk kadar sınırlayıcı `*/` sınırlayıcı, o satırdaki göz ardı edilir. Aksi takdirde, en fazla bir satırındaki metin `*/` sınırlayıcı desen eşleştirme kuralları aşağıdaki maddede açıklandığı tabi açıklamayı bir parçası olarak işlenir.

- İle başlayan bir sonraki satırların için `/**` sınırlayıcı, derleyici, isteğe bağlı beyaz boşluk ve yıldız oluşan her satırın başında yaygın bir düzen arar (`*`) ve ardından daha fazla isteğe bağlı beyaz boşluk. Derleyici, ortak bir karakter kümesi, her satırın başında bulursa, sonra tüm satırlar için bu düzeni yoksayacak `/**` sınırlayıcı, en fazla ve büyük olasılıkla içeren satırı dahil olmak üzere `*/` sınırlayıcı.

Bazı örnekler:

- Yalnızca işlenecek şu açıklama ile başlayan satırı parçasıdır `<summary>`. Aşağıdaki iki etiket biçimlerini aynı açıklamaları oluşturacak:

    ```cpp
    /**
    <summary>text</summary>
    */
    /** <summary>text</summary> */
    ```

- Derleyici desenini uygular " \* " ikinci ve üçüncü satır başında yok sayılacak.

    ```cpp
    /**
     * <summary>
     *  text </summary>*/
    ```

- İkinci satırda hiçbir yıldız işareti olduğundan derleyici Bu açıklamada yok desenini bulur. Bu nedenle, tüm metin ikinci ve üçüncü satırlardaki yukarı kasa `*/`, yorum bir parçası olarak işlenir.

    ```cpp
    /**
     * <summary>
       text </summary>*/
    ```

- Derleyici, iki nedenden dolayı bu açıklamada yok desenini bulur. İlk olarak, tutarlı bir yıldız işareti önceki boşluklar sayısı ile başlayan satırı yok yoktur. İkinci olarak, beşinci satır alanları eşleşmiyor bir sekme ile başlar. Bu nedenle, tüm metin kadar ikinci satırında `*/` açıklamayı bir parçası olarak işlenir.

    ```cpp
    /**
      * <summary>
      * text
     *  text2
       *  </summary>
    */
    ```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
