import streamlit as st
import pandas as pd
import numpy as np

# Configuration de la page Streamlit
st.set_page_config(page_title="JUNIOR PENSION - Calcul de Prime Commerciale", layout="wide")

# Données de la table de mortalité CIMA F
data = {
    "Age": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110],
    "Lx (CIMA F)": [1000000, 997151.4966, 996765.6321, 996470.3604, 996218.8441, 996003.906, 995807.9132, 995631.3848, 995464.8167, 995298.2594, 995141.828, 994975.292, 994808.7668, 994612.8641, 994379.5891, 994093.1546, 993715.6451, 993237.8452, 992644.1213, 991940.5015, 991157.5443, 990328.5698, 989470.4725, 988593.5765, 987701.3501, 986790.4266, 985860.8583, 984905.8717, 983925.5507, 982919.98, 981887.3127, 980831.4345, 979753.669, 978639.5807, 977475.0937, 976239.5096, 974933.877, 973545.4161, 972068.6251, 970491.5454, 968796.1978, 966965.442, 964970.436, 962808.3569, 960464.3022, 957929.855, 955196.7954, 952268.3988, 949153.1041, 945858.7621, 942387.2896, 938740.3592, 934903.4714, 930867.662, 926624.0395, 922158.62, 917467.7335, 912551.0665, 907329.4474, 901760.3828, 895756.9149, 889311.5924, 882341.0159, 874835.2593, 866785.1785, 858105.1904, 848789.6664, 838824.994, 828263.9255, 817076.1505, 805234.9104, 792705.8615, 779457.1759, 765474.658, 750740.1555, 735230.9587, 718908.4638, 701727.3171, 683655.1183, 664639.3132, 644582.2494, 623367.6145, 600904.5291, 577171.3438, 552228.2633, 526202.0961, 499208.8304, 471364.6651, 442823.4204, 413768.8204, 384431.3088, 355057.2463, 324274.8204, 290521.5964, 254286.8123, 216373.5056, 177917.6104, 140351.4623, 105287.9146, 74314.63704, 48718.4784, 29203.59882, 15705.81492, 7405.883675, 2977.685159, 986.9443547, 0, 0, 0, 0, 0],
    "dx (CIMA F)": [2848.503436, 385.8644478, 295.2716784, 251.5162978, 214.9380983, 195.9928909, 176.5283929, 166.5680654, 166.5572547, 156.431407, 166.5360139, 166.5252035, 195.902736, 233.2750223, 286.4344161, 377.509529, 477.7999516, 593.7238416, 703.6198547, 782.9571245, 828.9745568, 858.0972802, 876.8959543, 892.2264753, 910.9234834, 929.5683308, 954.9865624, 980.3210087, 1005.570719, 1032.667241, 1055.878182, 1077.765525, 1114.088355, 1164.487008, 1235.584025, 1305.632679, 1388.460824, 1476.791036, 1577.079681, 1695.347599, 1830.755768, 1995.006075, 2162.079119, 2344.054676, 2534.447131, 2733.059667, 2928.396532, 3115.294726, 3294.34206, 3471.472441, 3646.930461, 3836.887793, 4035.809384, 4243.622443, 4465.419492, 4690.886579, 4916.666965, 5221.619054, 5569.064666, 6003.467919, 6445.322509, 6970.576431, 7505.756582, 8050.080879, 8679.988083, 9315.523943, 9964.672433, 10561.06848, 11187.77502, 11841.24007, 12529.04891, 13248.68566, 13982.51785, 14734.50251, 15509.19682, 16322.49486, 17181.14676, 18072.19882, 19015.80505, 20057.06384, 21214.63485, 22463.08538, 23733.18536, 24943.0805, 26026.1672, 26993.26563, 27844.16538, 28541.24463, 29054.60004, 29337.51162, 29374.06248, 30782.42593, 33753.22399, 36234.78408, 37913.3067, 38455.89522, 37566.1481, 35063.54772, 30973.27753, 25596.15863, 19514.87958, 13497.7839, 8299.931242, 4428.198516, 1990.740804, 986.9443547, 0, 0, 0, 0, 0]
}
df = pd.DataFrame(data)

# Page de couverture
def display_cover_page():
    st.title("JUNIOR PENSION - Calcul de Prime Commerciale")
    st.markdown("""
    ### Projet d'Actuariat Vie
    **Membres du Groupe** : Doumbia Moussa, Tokpa Franck, Sanogo Karnon, Sossou Toussaint, Soro Maimouna 
    **Classe** : Master d'Actuariat  
    **Contexte** : Ce projet développe une application pour calculer la prime commerciale du produit "JUNIOR PENSION", une annuité différée temporaire conçue pour répondre aux besoins de financement de la retraite dans la zone CIMA. L'application utilise les tables de mortalité CIMA F et un taux d'intérêt technique de 4,0 %.

    Cliquez sur le bouton ci-dessous pour accéder à la calculatrice.
    """)
    if st.button("Accéder à la Calculatrice"):
        st.session_state.page = "calculator"

# Page de calcul
def display_calculator():
    st.title("Calculatrice de Prime Commerciale - JUNIOR PENSION")
    
    # Vérification des colonnes nécessaires
    required_columns = ["Age", "Lx (CIMA F)", "dx (CIMA F)"]
    missing_columns = [col for col in required_columns if col not in df.columns]
    if missing_columns:
        st.error(f"Les colonnes suivantes sont manquantes dans les données : {missing_columns}. Veuillez vérifier les noms des colonnes.")
        return

    # Extraction des colonnes nécessaires
    ages = df["Age"].values
    lx = df["Lx (CIMA F)"].values
    dx = df["dx (CIMA F)"].values

    # Vérification des données
    if len(ages) != len(lx) or len(lx) != len(dx):
        st.error("Les données sont incohérentes (tailles des colonnes différentes).")
        return

    # Paramètres d'entrée pour la prime commerciale
    st.header("Paramètres d'Entrée - Prime Commerciale")
    col1, col2 = st.columns(2)
    with col1:
        x = st.number_input("Âge à la souscription (x)", min_value=0, max_value=110, value=38, step=1)
        n = st.number_input("Période de différé (n, en années)", min_value=1, max_value=50, value=12, step=1)
        B = st.number_input("Capital décès (B, en FCFA)", min_value=0.0, value=3000000.0, step=1000.0)
    with col2:
        A1 = st.number_input("Annuité années 1-5 (A1, en FCFA)", min_value=0.0, value=1000000.0, step=1000.0)
        A2 = st.number_input("Annuité années 6-8 (A2, en FCFA)", min_value=0.0, value=700000.0, step=1000.0)
        A3 = st.number_input("Annuité années 9-10 (A3, en FCFA)", min_value=0.0, value=500000.0, step=1000.0)

    # Paramètres d'entrée pour la prime annuelle
    st.header("Paramètres d'Entrée - Prime Annuelle")
    col3, col4 = st.columns(2)
    with col3:
        fv = st.number_input("Valeur future (FV, en FCFA)", min_value=0.0, value=7778554.0, step=1000.0)
        r = st.number_input("Taux d'intérêt annuel (r, en %)", min_value=0.0, value=4.0, step=0.1) / 100
    with col4:
        n_annual = st.number_input("Durée (n, en années)", min_value=1, max_value=50, value=12, step=1)

    # Bouton pour calculer
    if st.button("Calculer les Primes"):
        # Calcul de la prime commerciale
        i = 0.04
        v = 1 / (1 + i)

        # Vérification des âges
        if x + n > 110 or x + n + 10 > 110:
            st.error("L'âge à la maturité ou pendant les paiements dépasse 110 ans, ce qui n'est pas supporté par la table de mortalité.")
            return

        # Calcul de la P.U.P.
        # Garantie décès : B * sum(v^t * (Lx+t-1 - Lx+t) / Lx) pour t=1 à n
        pv_deces = 0
        for t in range(1, n + 1):
            idx_x_t_minus_1 = np.where(ages == x + t - 1)[0]
            idx_x_t = np.where(ages == x + t)[0]
            if len(idx_x_t_minus_1) == 0 or len(idx_x_t) == 0:
                lx_t_minus_1 = 0
                lx_t = 0
            else:
                lx_t_minus_1 = lx[idx_x_t_minus_1[0]]
                lx_t = lx[idx_x_t[0]] if x + t <= 110 else 0
            prob_deces = (lx_t_minus_1 - lx_t) / lx[np.where(ages == x)[0][0]] if lx[np.where(ages == x)[0][0]] > 0 else 0
            pv_deces += v ** t * prob_deces
        pv_deces *= B

        # Garantie vie : v^n * (Lx+n / Lx) * [A1 * sum(v^t, t=1 à 5) + A2 * sum(v^t, t=6 à 8) + A3 * (v^9 * Lx+n+9/Lx+n + v^10 * Lx+n+10/Lx+n)]
        idx_x_n = np.where(ages == x + n)[0]
        lx_n = lx[idx_x_n[0]] if len(idx_x_n) > 0 else 0
        lx_x = lx[np.where(ages == x)[0][0]]
        prob_survie = lx_n / lx_x if lx_x > 0 else 0

        # Annuités certaines
        pv_a1 = sum(v ** t for t in range(1, 6)) * A1
        pv_a2 = sum(v ** t for t in range(6, 9)) * A2

        # Annuité viagère années 9-10
        idx_x_n_9 = np.where(ages == x + n + 9)[0]
        idx_x_n_10 = np.where(ages == x + n + 10)[0]
        lx_n_9 = lx[idx_x_n_9[0]] if len(idx_x_n_9) > 0 else 0
        lx_n_10 = lx[idx_x_n_10[0]] if len(idx_x_n_10) > 0 else 0
        prob_survie_9 = lx_n_9 / lx_n if lx_n > 0 else 0
        prob_survie_10 = lx_n_10 / lx_n if lx_n > 0 else 0
        pv_a3 = A3 * (v ** 9 * prob_survie_9 + v ** 10 * prob_survie_10)

        pv_vie = v ** n * prob_survie * (pv_a1 + pv_a2 + pv_a3)

        pup = pv_deces + pv_vie

        # Frais sur prestations
        # Décès : (1000 + 0.005 * B) * sum(v^t * (Lx+t-1 - Lx+t) / Lx)
        frais_deces = 0
        for t in range(1, n + 1):
            idx_x_t_minus_1 = np.where(ages == x + t - 1)[0]
            idx_x_t = np.where(ages == x + t)[0]
            if len(idx_x_t_minus_1) == 0 or len(idx_x_t) == 0:
                lx_t_minus_1 = 0
                lx_t = 0
            else:
                lx_t_minus_1 = lx[idx_x_t_minus_1[0]]
                lx_t = lx[idx_x_t[0]] if x + t <= 110 else 0
            prob_deces = (lx_t_minus_1 - lx_t) / lx[np.where(ages == x)[0][0]] if lx[np.where(ages == x)[0][0]] > 0 else 0
            frais_deces += v ** t * prob_deces
        frais_deces *= (1000 + 0.005 * B)

        # Annuités : 0.2 * [A1 * sum(v^(n+t), t=1 à 5) + A2 * sum(v^(n+t), t=6 à 8) + A3 * (v^(n+9) * Lx+n+9/Lx+n + v^(n+10) * Lx+n+10/Lx+n)]
        frais_vie = 0.2 * (
            A1 * sum(v ** (n + t) for t in range(1, 6)) +
            A2 * sum(v ** (n + t) for t in range(6, 9)) +
            A3 * (v ** (n + 9) * prob_survie_9 + v ** (n + 10) * prob_survie_10)
        )

        vap_frais = frais_deces + frais_vie

        # Prime commerciale : P = (P.U.P. + VAP_Frais + 5000) / (1 - 0.35)
        prime_commerciale = (pup + vap_frais + 5000) / (1 - 0.35)

        # Calcul de la prime annuelle
        try:
            denominator = (1 + r) ** n_annual - 1
            if denominator == 0:
                st.error("Erreur : Division par zéro dans le calcul de la prime annuelle (taux ou durée invalide).")
                return
            prime_annuelle = (fv * r) / denominator
        except Exception as e:
            st.error(f"Erreur dans le calcul de la prime annuelle : {str(e)}")
            return

        # Affichage des résultats
        st.header("Résultats")
        st.subheader("Prime Commerciale")
        st.write(f"**Prime Pure Unique (P.U.P.)** : {pup:,.2f} FCFA")
        st.write(f"**Valeur Actuelle des Frais sur Prestations** : {vap_frais:,.2f} FCFA")
        st.write(f"**Prime Commerciale** : {prime_commerciale:,.2f} FCFA")
        st.subheader("Prime Annuelle")
        st.write(f"**Prime Annuelle** : {prime_annuelle:,.2f} FCFA")

# Gestion des pages
if "page" not in st.session_state:
    st.session_state.page = "cover"

if st.session_state.page == "cover":
    display_cover_page()
else:
    display_calculator()
