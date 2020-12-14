---
description: 'Daha fazla bilgi: Visual C++ belge etiketleri için sınırlayıcılar'
title: Visual C++ Belge Etiketleri için Sınırlayıcılar
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
ms.openlocfilehash: 7878fa0454af9eb09c4aa537a3e59d8af4a3ee87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201475"
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Visual C++ Belge Etiketleri için Sınırlayıcılar

Belge etiketlerinin kullanımı, bir belge açıklamasının başladığı ve bittiği derleyiciye işaret eden sınırlayıcılar gerektirir.

XML belge etiketleriyle aşağıdaki tür sınırlayıcıları kullanabilirsiniz:

| Sınırlayıcı | Açıklama |
|-|-|
| `///` | Bu, belge örneklerinde gösterilen ve Visual Studio C++ proje şablonları tarafından kullanılan formdur.  |
| `/** */`  | Bunlar çok satırlı sınırlayıcılardır.  |

Sınırlayıcılar kullanılırken bazı biçimlendirme kuralları vardır `/** */` :

- Sınırlayıcısı içeren çizgi için `/**` , satırın geri kalanı boşluk ise, satır Yorumlar için işlenmez. İlk karakter boşluk ise, bu boşluk karakteri yok sayılır ve satırın geri kalanı işlenir. Aksi halde, ayırıcıdan sonraki satırın metnin tamamı `/**` açıklamanın bir parçası olarak işlenir.

- Sınırlandırıcıyı içeren çizgi için `*/` , sınırlandırıcının yalnızca beyaz alanı varsa `*/` , bu satır yok sayılır. Aksi takdirde, ayırıcıya kadar olan satırdaki metin `*/` , açıklamanın bir parçası olarak işlenir ve bu, aşağıdaki madde işaretinde açıklanan desenler ile eşleşen kurallara tabidir.

- Sınırlayıcı ile başlayan satırlar için `/**` , derleyici isteğe bağlı boşluk ve yıldız işareti () içeren her bir satırın başlangıcında ortak bir model arar ve `*` ardından daha isteğe bağlı boşluk gelir. Derleyici, her satırın başlangıcında ortak bir karakter kümesi bulursa, sınırlayıcıdan sonra gelen tüm satırların bu deseninin ölçeğini yok sayarak `/**` sınırlayıcı içeren satırı dahil eder `*/` .

Bazı örnekler:

- Aşağıdaki açıklamanın işlenecek tek bir bölümü, ile başlayan satırdır `<summary>` . Aşağıdaki iki etiket biçimi de aynı açıklamaları üretir:

    ```cpp
    /**
    <summary>text</summary>
    */
    /** <summary>text</summary> */
    ```

- Derleyici, \* ikinci ve üçüncü çizgilerin başlangıcında yok saymak için bir "" kalıbı uygular.

    ```cpp
    /**
     * <summary>
     *  text </summary>*/
    ```

- İkinci satırda bir yıldız işareti olmadığından, derleyici bu açıklamada hiç bir model yok. Bu nedenle, ikinci ve üçüncü satırlardaki tüm metinler, `*/` açıklamanın bir parçası olarak işlenir.

    ```cpp
    /**
     * <summary>
       text </summary>*/
    ```

- Derleyici, bu açıklamada iki nedenden dolayı hiçbir model bulmamalıdır. İlk olarak, yıldız işareti öncesinde tutarlı sayıda boşluk ile başlayan bir satır yoktur. İkincisi, beşinci satır boşluk ile eşleşmeyen bir sekme ile başlar. Bu nedenle, `*/` açıklamanın bir parçası olarak işlenene kadar ikinci satırdaki tüm metinler.

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
