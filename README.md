# sample

{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/takanabe2001/python/blob/main/ch01_ipynb_%E3%81%AE%E3%82%B3%E3%83%94%E3%83%BC.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#00. 文字列の逆順\n",
        "文字列”stressed”の文字を逆に（末尾から先頭に向かって）並べた文字列を得よ．"
      ],
      "metadata": {
        "id": "zqgSKhr0nb7K"
      }
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "OvEVPTfOnaWw",
        "outputId": "1daebb13-6c76-4a7a-bc48-4eea9de74251"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "desserts\n"
          ]
        }
      ],
      "source": [
        "s = \"stressed\"\n",
        "print(s[::-1])"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"stressed\"\n",
        "# reversed()を使用 : 文字列、リスト、タプルを逆にする\n",
        "result = ''.join(reversed(s))\n",
        "print(result)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "GV2KFW12ZAs4",
        "outputId": "e9544ff0-fa84-4ae0-d2d2-7500464e760a"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "desserts\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#01. 「パタトクカシーー」\n",
        "「パタトクカシーー」という文字列の1,3,5,7文字目を取り出して連結した文字列を得よ"
      ],
      "metadata": {
        "id": "KrYW7n_fnsMe"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"パタトクカシーー\"\n",
        "print(s[0] + s[2] + s[4] + s[6])"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "P5K48i8FnwWs",
        "outputId": "7e046ce5-8627-497e-be12-c0fca40ec2f7"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "パトカー\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"パタトクカシーー\"\n",
        "#方法1\n",
        "#1から一個飛ばし(奇数だけ取得)して結合\n",
        "result = ''.join([s[i] for i in range(1, len(s), 2)])\n",
        "# result = s[1::2]\n",
        "print(result)\n",
        "#方法2\n",
        "#自分で指定した位置の文字列だけ取得して結合\n",
        "target = [1,3,5,7]\n",
        "result = ''.join([s[i] for i in target])\n",
        "print(result)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "2zSbVqqLZa4X",
        "outputId": "72b9ef5d-90b7-427e-abf6-bd03549e3c56"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "タクシー\n",
            "タクシー\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#02. 「パトカー」＋「タクシー」＝「パタトクカシーー」\n",
        "「パトカー」＋「タクシー」の文字を先頭から交互に連結して文字列「パタトクカシーー」を得よ"
      ],
      "metadata": {
        "id": "8A4Fga95nw7b"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "s1 = \"パトカー\"\n",
        "s2 = \"タクシー\"\n",
        "print(\"\".join([i+j for i, j in zip(s1, s2)]))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "rLoLpVUbn0nU",
        "outputId": "64ae3ddc-b572-4d35-9556-cab10a9fcb51"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "パタトクカシーー\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "s1 = \"パトカー\"\n",
        "s2 = \"タクシー\"\n",
        "# 文字列の長さを取得して(短い方基準）、ループで結合していく\n",
        "result = \"\".join([(s1[i] + s2[i]) for i in range(min(len(s1), len(s2)))])\n",
        "print(result)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "chi-m_SpbZbz",
        "outputId": "b07d8ef9-b5eb-4d49-88cd-f7f1a720c130"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "パタトクカシーー\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "s1 = \"パトカー\"\n",
        "s2 = \"タクシー\"\n",
        "result = \"\"\n",
        "# 文字列の長さを取得して(短い方基準）、ループで結合していく\n",
        "result = result.join([(s1[i] + s2[i]) for i in range(min(len(s1), len(s2)))])\n",
        "print(result)"
      ],
      "metadata": {
        "id": "iCVv-YRyqFLJ",
        "outputId": "7405f05d-2f90-4d4f-dbd5-742983d9154f",
        "colab": {
          "base_uri": "https://localhost:8080/"
        }
      },
      "execution_count": 3,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "パタトクカシーー\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#03. 円周率\n",
        "“Now I need a drink, alcoholic of course, after the heavy lectures involving quantum mechanics.”という文を単語に分解し，各単語の（アルファベットの）文字数を先頭から出現順に並べたリストを作成せよ．"
      ],
      "metadata": {
        "id": "u0ZSsqMHn1Fj"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"Now I need a drink, alcoholic of course, after the heavy lectures involving quantum mechanics.\"\n",
        "print([len(i) for i in s.replace(\",\", \"\").replace(\".\", \"\").split()])"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "lujt_ehTn3ux",
        "outputId": "ff655320-5c85-4f9b-eb64-11e5b992b00b"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "[3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5, 8, 9, 7, 9]\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"Now I need a drink, alcoholic of course, after the heavy lectures involving quantum mechanics.\"\n",
        "word_lengths = [len(word.strip('.,')) for word in s.split() if len(word.strip(',.')) != 3]\n",
        "print(word_lengths)\n",
        "# # 分解\n",
        "# s_split = s.split() #空白で区切って、リストに格納\n",
        "# print(s_split)\n",
        "# word_lengths = []\n",
        "# for word in s_split:\n",
        "#     word = word.strip('.,') #先頭および末尾の.と,を削除\n",
        "#     word_lengths.append(len(word)) #文字数かぞえて、リストに追加\n",
        "# print(word_lengths)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "m2FGQ6y1cdTA",
        "outputId": "4a733f5c-c369-444a-fb03-29980681ee85"
      },
      "execution_count": 4,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "[1, 4, 1, 5, 9, 2, 6, 5, 5, 8, 9, 7, 9]\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#04. 元素記号\n",
        "“Hi He Lied Because Boron Could Not Oxidize Fluorine. New Nations Might Also Sign Peace Security Clause. Arthur King Can.”という文を単語に分解し，1, 5, 6, 7, 8, 9, 15, 16, 19番目の単語は先頭の1文字，それ以外の単語は先頭の2文字を取り出し，取り出した文字列から単語の位置（先頭から何番目の単語か）への連想配列（辞書型もしくはマップ型）を作成せよ．"
      ],
      "metadata": {
        "id": "uEveeiYon4H5"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"Hi He Lied Because Boron Could Not Oxidize Fluorine. New Nations Might Also Sign Peace Security Clause. Arthur King Can.\"\n",
        "l = s.split()\n",
        "num = [1, 5, 6, 7, 8, 9, 15, 16, 19]\n",
        "d = {}\n",
        "\n",
        "for i, e in enumerate(l):\n",
        "  if i+1 in num:\n",
        "    d[e[0]] = i+1\n",
        "  else:\n",
        "    d[e[:2]] = i+1\n",
        "\n",
        "print(d)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "OsOHOQB1n9ya",
        "outputId": "f3595264-65f2-4cfd-c698-eda2553c99dc"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "{'H': 1, 'He': 2, 'Li': 3, 'Be': 4, 'B': 5, 'C': 6, 'N': 7, 'O': 8, 'F': 9, 'Ne': 10, 'Na': 11, 'Mi': 12, 'Al': 13, 'Si': 14, 'P': 15, 'S': 16, 'Cl': 17, 'Ar': 18, 'K': 19, 'Ca': 20}\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "s = \"Hi He Lied Because Boron Could Not Oxidize Fluorine. New Nations Might Also Sign Peace Security Clause. Arthur King Can.\"\n",
        "selected_indices = [1, 5, 6, 7, 8, 9, 15, 16, 19]\n",
        "#上のやつを短く記述したやつ\n",
        "element_dict = {word[:1] if i + 1 in selected_indices else word[:2] :i + 1 for i, word in enumerate(s.split())}\n",
        "print(element_dict)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "uBNjBzhSfEcK",
        "outputId": "02645e24-a92f-42ee-dfc1-eb02d553204f"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "{'H': 1, 'He': 2, 'Li': 3, 'Be': 4, 'B': 5, 'C': 6, 'N': 7, 'O': 8, 'F': 9, 'Ne': 10, 'Na': 11, 'Mi': 12, 'Al': 13, 'Si': 14, 'P': 15, 'S': 16, 'Cl': 17, 'Ar': 18, 'K': 19, 'Ca': 20}\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#05. n-gram\n",
        "与えられたシーケンス（文字列やリストなど）からn-gramを作る関数を作成せよ．この関数を用い，”I am an NLPer”という文から単語bi-gram，文字bi-gramを得よ．"
      ],
      "metadata": {
        "id": "JqgiHWvFn_ME"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "def n_gram(sequence, mode=0): # 0:単語, 1:文字\n",
        "  bi_gram = []\n",
        "  if mode == 0: # 単語bigram\n",
        "    l = sequence.split()\n",
        "    for i in range(len(l)-1):\n",
        "      bi_gram.append(l[i]+l[i+1])\n",
        "  elif mode == 1: # 文字bigram\n",
        "    s = sequence.replace(\" \", \"\")\n",
        "    for i in range(len(s)-1):\n",
        "      bi_gram.append(s[i]+s[i+1])\n",
        "\n",
        "  return \" \".join(bi_gram)\n",
        "\n",
        "print(n_gram(\"I am an NLPer\", mode=0))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "jbmBEWX6oCek",
        "outputId": "b309a692-4ea0-4c98-b78a-c5b35222c7c9"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Iam aman anNLPer\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "def n_gram(sequence, n):\n",
        "    return [sequence[i:i+n] for i in range(len(sequence)-n+1)]\n",
        "\n",
        "sentence = \"I am an NLPer\"\n",
        "word_bi_gram = [a + b for a, b in n_gram(sentence.split(), 2)]\n",
        "char_bi_gram = n_gram(sentence.replace(\" \", \"\"), 2) #空白を削除して関数に渡す(単語の区別をなくす->ただの文字列にする)\n",
        "\n",
        "print(\"単語Bi-gram:\", word_bi_gram)\n",
        "print(\"文字Bi-gram:\", char_bi_gram)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "kvOsahuFgwEO",
        "outputId": "51b0959c-fcc3-4404-ac8c-7eac6871c8fe"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "単語Bi-gram: ['Iam', 'aman', 'anNLPer']\n",
            "文字Bi-gram: ['Ia', 'am', 'ma', 'an', 'nN', 'NL', 'LP', 'Pe', 'er']\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#06. 集合\n",
        "“paraparaparadise”と”paragraph”に含まれる文字bi-gramの集合を，それぞれ, XとYとして求め，XとYの和集合，積集合，差集合を求めよ．さらに，’se’というbi-gramがXおよびYに含まれるかどうかを調べよ．"
      ],
      "metadata": {
        "id": "y9h5gMdZoC5x"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "s1 = \"paraparaparadise\"\n",
        "s2 = \"paragraph\"\n",
        "\n",
        "x = set(n_gram(s1, mode=1).split())\n",
        "y = set(n_gram(s2, mode=1).split())\n",
        "\n",
        "print(\"和集合：{}\".format(x | y))\n",
        "print(\"積集合：{}\".format(x & y))\n",
        "print(\"差集合：{}\".format(x - y))\n",
        "\n",
        "print(\"Xに'se'は含まれている→{}\".format(\"se\" in x))\n",
        "print(\"Yに'se'は含まれている→{}\".format(\"se\" in y))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "kZlqPASvoFOU",
        "outputId": "f3e94cd5-e630-46e3-8677-2da796ee104d"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "和集合：{'gr', 'pa', 'ra', 'di', 'se', 'is', 'ad', 'ap', 'ar', 'ag', 'ph'}\n",
            "積集合：{'ra', 'ap', 'ar', 'pa'}\n",
            "差集合：{'is', 'di', 'ad', 'se'}\n",
            "Xに'se'は含まれている→True\n",
            "Yに'se'は含まれている→False\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "X = set(n_gram(\"paraparaparadise\", 2))\n",
        "Y = set(n_gram(\"paragraph\", 2))\n",
        "\n",
        "# 関数使用\n",
        "union = X.union(Y)  # 和集合\n",
        "intersection = X.intersection(Y)  # 積集合\n",
        "difference_X = X.difference(Y)  # 差集合\n",
        "difference_Y = Y.difference(X)  # 差集合\n",
        "\n",
        "#\"se\"がXに入っているか\n",
        "check_X = \"se\" in X\n",
        "\n",
        "#\"se\"がYに入っているか\n",
        "check_Y = \"se\" in Y\n",
        "\n",
        "print(\"X:\", X)\n",
        "print(\"Y:\", Y)\n",
        "print(\"和集合:\", union)\n",
        "print(\"積集合:\", intersection)\n",
        "print(\"差集合 X-Y:\", difference_X)\n",
        "print(\"差集合 Y-X:\", difference_Y)\n",
        "print(\"'se' in X:\", check_X)\n",
        "print(\"'se' in Y:\", check_Y)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "8zzGHJV6kPFH",
        "outputId": "7f77609f-80a9-468c-9580-da846e7e163a"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "X: {'di', 'ad', 'ap', 'se', 'ar', 'is', 'ra', 'pa'}\n",
            "Y: {'gr', 'ap', 'ph', 'ar', 'ra', 'ag', 'pa'}\n",
            "和集合: {'di', 'ad', 'ap', 'gr', 'ph', 'se', 'ar', 'is', 'ra', 'ag', 'pa'}\n",
            "積集合: {'ap', 'ar', 'ra', 'pa'}\n",
            "差集合 X-Y: {'is', 'di', 'ad', 'se'}\n",
            "差集合 Y-X: {'gr', 'ag', 'ph'}\n",
            "'se' in X: True\n",
            "'se' in Y: False\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#07. テンプレートによる文生成\n",
        "引数x, y, zを受け取り「x時のyはz」という文字列を返す関数を実装せよ．さらに，x=12, y=”気温”, z=22.4として，実行結果を確認せよ．"
      ],
      "metadata": {
        "id": "gSC6D05_oFoJ"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "def xyz(x, y, z):\n",
        "  print(\"{}時の{}は{}\".format(x, y, z))\n",
        "\n",
        "xyz(x=12, y=\"気温\", z=22.4)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "yf4yuxt9oH9N",
        "outputId": "e2942f5a-eecc-47ed-ae03-8625eea63012"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "12時の気温は22.4\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "def gen_sent(x, y, z):\n",
        "    return f\"{x}時の{y}は{z}\" #f文字列(3.6以上) : 文字列内に変数を埋め込むことができる\n",
        "\n",
        "result = gen_sent(x=12, y=\"気温\", z=22.4)\n",
        "print(result)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "7FYnla3Mlr65",
        "outputId": "fbab1653-f846-475e-8581-b2b0ba7076e4"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "12時の気温は22.4\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#08. 暗号文\n",
        "与えられた文字列の各文字を，以下の仕様で変換する関数cipherを実装せよ．\n",
        "\n",
        "英小文字ならば(219 - 文字コード)の文字に置換\n",
        "その他の文字はそのまま出力\n",
        "この関数を用い，英語のメッセージを暗号化・復号化せよ．"
      ],
      "metadata": {
        "id": "p7M2ZapEoILf"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "def cipher(s):\n",
        "  cry = []\n",
        "  for i in s:\n",
        "    if i.islower():\n",
        "      cry.append(chr(219 - ord(i)))\n",
        "    else:\n",
        "      cry.append(i)\n",
        "\n",
        "  return \"\".join(cry)\n",
        "\n",
        "print(cipher(\"I am an NLPer\"))\n",
        "print(cipher(cipher(\"I am an NLPer\")))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "iXIeO4iWoLLv",
        "outputId": "ae7f5dc4-d9ae-4ad9-8d4d-2b0a98cf33b5"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "I zn zm NLPvi\n",
            "I am an NLPer\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# 上のやつを短くしたやつ\n",
        "def cipher(text):\n",
        "    return ''.join([chr(219 - ord(char)) if char.islower() else char for char in text])\n",
        "\n",
        "message = \"I am an NLPer\"\n",
        "encrypted_message = cipher(message)\n",
        "decrypted_message = cipher(encrypted_message)\n",
        "\n",
        "print(\"Original:\", message)\n",
        "print(\"Encrypted:\", encrypted_message)\n",
        "print(\"Decrypted:\", decrypted_message)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "L9m78G4Nmwqw",
        "outputId": "cb60ba7f-43c5-4dfb-9f18-8deb11d4ee93"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Original: I am an NLPer\n",
            "Encrypted: I zn zm NLPvi\n",
            "Decrypted: I am an NLPer\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#09. Typoglycemia\n",
        "スペースで区切られた単語列に対して，各単語の先頭と末尾の文字は残し，それ以外の文字の順序をランダムに並び替えるプログラムを作成せよ．ただし，長さが４以下の単語は並び替えないこととする．適当な英語の文（例えば”I couldn’t believe that I could actually understand what I was reading : the phenomenal power of the human mind .”）を与え，その実行結果を確認せよ．"
      ],
      "metadata": {
        "id": "OK9jlMxLoLj8"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "import random\n",
        "\n",
        "s = \"I couldn’t believe that I could actually understand what I was reading : the phenomenal power of the human mind .\"\n",
        "l = []\n",
        "\n",
        "for i in s.split():\n",
        "\n",
        "  if len(i) <= 4:\n",
        "    l.append(i)\n",
        "  else:\n",
        "    m = i[1:-1]\n",
        "    l.append(i[0] + \"\".join(random.sample(m, len(m))) + i[-1])\n",
        "\n",
        "print(\" \".join(l))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "N2ixSMLtoOK_",
        "outputId": "1aa2f3e5-dcc6-4bba-b24c-b3b5ab1103f5"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "I c’ulondt beievle that I culod alauclty uesdtnanrd what I was rnieadg : the pnaohnemel peowr of the hmaun mind .\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import random\n",
        "\n",
        "def typoglycemia(sentence):\n",
        "    words = sentence.split()\n",
        "    result = [word if len(word) <= 4 else word[0] + ''.join(random.sample(word[1:-1], len(word)-2)) + word[-1] for word in words]\n",
        "    return ' '.join(result)\n",
        "\n",
        "s = \"I couldn't believe that I could actually understand what I was reading : the phenomenal power of the human mind .\"\n",
        "result = typoglycemia(s)\n",
        "print(result)"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "7V5DcVoanL4d",
        "outputId": "8d4b9ba7-c050-4943-ed1b-a3caf7eda6d1"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "I c'odulnt biveele that I cloud aucltaly usnaerndtd what I was ridaeng : the pmnhaoenel pewor of the hmaun mind .\n"
          ]
        }
      ]
    }
  ]
}
