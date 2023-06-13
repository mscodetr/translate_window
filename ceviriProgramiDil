from PyQt5 import QtWidgets
import sys
from ceviri2 import Ui_MainWindow
import translate


class myApp(QtWidgets.QMainWindow):
    def cevir(self):
        dil = self.ui.cmb_dil.currentText()
        result_text = self.ui.txt_metin.text()

        if not result_text.strip():
            # Metin kutusu boşsa veya sadece boşluklardan oluşuyorsa hata işleyin veya uygun bir değer atayın
            return

        result = int(result_text)

        translator = None
        if dil == 'Korece':
            translator = translate.Translator(from_lang="tr", to_lang="ko")
        elif dil == 'Özbekçe':
            translator = translate.Translator(from_lang="tr", to_lang="uz")
        elif dil == 'Japonca':
            translator = translate.Translator(from_lang="tr", to_lang="ja")

        if translator is not None:
            translation = translator.translate(result)
            self.ui.txt_ceviri.setText(translation)

    def __init__(self):
        super(myApp, self).__init__()
        self.ui = Ui_MainWindow()
        self.ui.setupUi(self)
        self.ui.btn_cevir.clicked.connect(self.cevir)
        self.ui.btn_ko.clicked.connect(self.cevir)
        self.ui.btn_uz.clicked.connect(self.cevir)
        self.ui.btn_ja.clicked.connect(self.cevir)


def app():
    app = QtWidgets.QApplication(sys.argv)
    win = myApp()
    win.show()
    sys.exit(app.exec_())


app()
