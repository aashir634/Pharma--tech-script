# Simple Drug-Drug Interaction (DDI) Checker
# Demonstrating the intersection of clinical data and Python programming.

interactions_db = {
    ("Aspirin", "Warfarin"): "High Risk: Increased risk of bleeding.",
    ("Lisinopril", "Potassium"): "Moderate Risk: Elevated risk of hyperkalemia.",
    ("Omeprazole", "Clopidogrel"): "High Risk: Decreased antiplatelet effectiveness."
}

def check_interaction(drug1, drug2):
    pair = (drug1.capitalize(), drug2.capitalize())
    reverse_pair = (drug2.capitalize(), drug1.capitalize())
    
  if pair in interactions_db:
        return interactions_db[pair]
    elif reverse_pair in interactions_db:
        return interactions_db[reverse_pair]
    else:
        return "No known interaction found in the local database."

# Testing the function
drug_a = "Aspirin"
drug_b = "Warfarin"
print(f"Clinical Alert for {drug_a} + {drug_b}:")
print(check_interaction(drug_a, drug_b))
